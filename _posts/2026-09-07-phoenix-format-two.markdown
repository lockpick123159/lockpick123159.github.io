---
layout: page
title: Format Two
permalink: /phoenix/
---

I use the book "The Shellcoder's Handbook: Discovering and Exploiting Security Holes" as a textbook for this CTF. It presents the direct paramater access in a format string to skip over format arguments. However, this is not fully supported in the c library used for this program since it uses "musl" libc library. If you want to use `%i%n` the ith arguemnt. You must first have referenced `%1$n` `%2$n` ... `%(i-1)$n`.
