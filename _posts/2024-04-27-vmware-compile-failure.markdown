---
layout: post
title: "Kernel header compile error for Vmware Workstation Pro 17 on Fedora 6.8.7-300.fc40.x86_64"
---

# The Problem
I was trying to run Vmware Workstation Pro 17 after updating to Fedora 6.8.7-300.fc40.x86_64 and it failed. Vmware spat out a log for why Vmware failed: [vmware-72431.log]({{iste.url}}/assets/vmware-72431.log). The crucial part of this log is the compile error:
```
2024-04-27T06:18:06.233Z In(05) host-72431 ./arch/x86/include/asm/timex.h:12:24: error: implicit declaration of function ‘random_get_entropy_fallback’; did you mean ‘random_get_entropy’? [-Wimplicit-function-declaration]
2024-04-27T06:18:06.233Z In(05) host-72431    12 |                 return random_get_entropy_fallback();
2024-04-27T06:18:06.233Z In(05) host-72431       |                        ^~~~~~~~~~~~~~~~~~~~~~~~~~~
2024-04-27T06:18:06.233Z In(05) host-72431       |                        random_get_entropy
```

# Solution
`# cd /usr/src/kernels/6.8.7-300.fc40.x86_64/arch/x86/include/asm/`

`# cp timex.h timex.h.original`

Now open the file and go to the error and replace `random_get_entrophy_fallback` to `random_get_entrophy`. It should be fixed now.


