---
layout: page
title: Format Two
---

I use the book "The Shellcoder's Handbook: Discovering and Exploiting Security Holes" as a textbook for this CTF. It presents the direct paramater access in a format string to skip over format arguments. However, this is not fully supported in the c library used for this program since it uses "musl" libc library. If you want to use `%i%n` the ith argument. You must first have referenced `%1$n` `%2$n` ... `%(i-1)$n`. 
```
       If the style using '$' is used, it must be used throughout for all
       conversions taking an argument and all width and precision
       arguments, but it may be mixed with "%%" formats, which do not
       consume an argument.  There may be no gaps in the numbers of
       arguments specified using '$'; for example, if arguments 1 and 3
       are specified, argument 2 must also be specified somewhere in the
       format string.
```

Please refer to the [manpage of `printf`](https://man7.org/linux/man-pages/man3/printf.3.html).
