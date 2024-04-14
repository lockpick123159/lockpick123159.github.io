---
layout: post
title: "Solution to Computer Systems: A Programmer's Perspective"
---

## Chapter 1

\\[\begin{align}S = \frac{1}{(1-\alpha)+\alpha/k\} && \text{(Amdahl's Law)} \end{align}\\]

# Practice Problem 1.1

![1.1.png]({{site.url}}/assets/1.1.png)

A. It takes 25 hours to travel from Boise to Minneapolis and travelling through Montana takes 20 hours. Thus \\(\alpha = \frac{\text{20hr}}{\text{25hr}} = 0.6\\). The average speed improved from \\(\text{100km/hr}\\) to \\(\text{150km/hr}\\). Thus, \\(k=\frac{\text{150km/hr}}{\text{100km/hr}}=1.5\\). By Amdahl's law, \\(S=\frac{1}{(1-0.6 + 0.6/1.5)}=1.25\\).

B. If we rearrange Amdhal's law for \\(k\\), we get 
\\[k=\frac{\alpha S}{1+S(\alpha-1)}\\]

Let \\(v\\) represent the speed at which the vehicle travels through Montana. Then, \\[\alpha = \frac{\text{1500km}/v + (\text{1000km}/ \text{100km/hr})}{\text{25hr}} \\]. Given \\(S = 1.67\\), we have \\[\frac{v}{100} = \frac{1.67(\frac{\text{10hr}\cdot v + \text{1500km}}{\text{25hr}\cdot v})} {1 + 1.67(\frac{\text{(10hr)}\cdot v + 1500km}{\text{25hr}\cdot v}-1)}\\]. Thus, \\(v=\text{305.56km/hr}\\)

# Practice Problem 1.2

Given \\(\alpha=0.9\\) and \\(S=4\\), we have to improve 90% of this machine by a factor of \\(k=\frac{(0.9)(0.4)}{1+4\cdot (0.9-1)} = 6\\)