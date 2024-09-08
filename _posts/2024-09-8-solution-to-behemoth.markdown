---
layout: post
title: "Strategies to solving Behemoth"
---

These problems have already been tried and solved by the author. As advised by OverTheWire, I will not post direct answers to these problems, however offer stratigies, which were used to conquer them.

# Behemoth0
The commnad `strings` show a bunch of strings that look like the answer to this problem, however these are all meant to deceive you.
Set a breakpoint at the function `strcmp` to see the actual string your input is being compared to.

# Behemoth1
Our [shellcode](https://shell-storm.org/shellcode/files/shellcode-250.html) is 33 bytes and the buffer 68 bytes is too small for a reliable exploit; the remaining space 35 bytes is not enough to be used as a nop sled. We have to utilize the environment variable to overcome this space problem. Save your nop slide and shellcode in an environment variable and jump to the address of the nop sled.