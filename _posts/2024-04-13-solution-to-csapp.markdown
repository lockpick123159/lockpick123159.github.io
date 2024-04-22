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

## Chapter 2

# Practice Problem 2.1
A. \\( (\text{0010 0101 1011 1001 1101 0010})_{2} \\)

B. \\( (\text{AE49})_{16}\\)

C. \\( (\text{1010 1000 1011 0011 1101})_2 \\)

D. \\( (\text{322D96})_{16} \\)

# Practice Problem 2.2

| \\(n\\) | \\(2^n\\)(decimal)  | \\(2^n\\)(hexadecimal) |
| -----   | ------------------  | ---------------------- |
|   5     |         32          |          0x20          |
|   23    |       8388608       |          0x800000      |
|   15    |        32768        |          0x8000        |
|   13    |        8192         |          0x2000        |
|   12    |        4096         |          0x1000        |
|   6     |         64          |          0x40          |
|   8     |        256          |          0x100         |

# Practice Problem 2.3

| Decimal | Binary    | Hexadecimal |
| ------- | ------    | ----------- |
|   0     | 0000 0000 |    0x00     |
|   158   | 1001 1110 |    0x9E     |
|   76    | 0100 1100 |    0x4C     |
|   145   | 1001 0001 |    0x91     |
|   174   | 1010 1110 |    0xAE     |
|   60    | 0011 1100 |    0x3C     |
|   241   | 1111 0001 |    0xF1     |

# Practice Problem 2.4
A. 0x6061

B. 0x603C

C. 0x607c

D. 0x9c

# Practice Problem 2.5

A. Little endian: 0x78      Big endian: 0x12
B. Little endian: 0x7856    Big endian: 0x1234
C. Little endian: 0x785634  Big endian: 0x123456

# Practice Problem 2.6

A. \\(\begin{align} \text{0x0027C8F8 = 0000 0000 0010 0111 1100 1000 1111 1000} \\\ \text{0x4A1F23E0 = 0100 1010 0001 1111 0010 0011 1110 0000}\end{align}\\)

B.
\\(\begin{align}\text{0x0027c8f8 = 0000 0000 0010} \textbf{ 0111 1100 1000 1111 1000} \\\ \text{0x4A1F23E0} \gg \text{2 = 0001 0010 1000} \textbf{ 0111 1100 1000 1111 1000} && \text{(20 bits)}\end{align}\\)  
C. See 2.6 B

# Practice Problem 2.7

\\(\text{0x7271706F6E6D\}\\)

# Practice Problem 2.8

| Operation            |     Result       |
| ---------            |     ------       |
| \\(a\\)              | \\([01001110]\\) |
| \\(b\\)              | \\([11100001]\\) |
| \\(\sim a\\)         | \\([10010110]\\) |
| \\(\sim b\\)         | \\([10101010]\\) |
| \\(a\& b\\)          | \\([01000001]\\) |
| \\(a \| b \\)        | \\([01111101]\\) | 
| \\(a^\widehat{} b\\) | \\([00111100]\\) |

# Practice Problem 2.9

A.

| Colour  | Complement |
| ------  | ---------- |
| Black   | \\(111\\)  |
| Blue    | \\(110\\)  |
| Green   | \\(101\\)  |
| Cyan    | \\(100\\)  |
| Red     | \\(011\\)  |
| Magenta | \\(010\\)  |
| Yellow  | \\(001\\)  |
| White   | \\(000\\)  |

B.

\\(\begin{align} \text{Blue} \| \text{Green} &= \text{Cyan} \\\ \text{Yellow} \& \text{Cyan} &= \text{Blue} \\\ \text{Red}^\widehat{} \text{Magenta} &= \text{Blue} \end{align} \\)

# Practice Problem 2.10

| Step      | *x        | * y       | 
| ----      | ----      | ----      |
| Initially | a         | b         |       
| Step 1    | a         | a^b       |
| Step 2    | a^a^b = b | a^b       |
| Step 3    | b         | b^a^b = a |

# Practice Problem 2.11

A. \\(\lceil{\frac{2k+1}{2}}\rceil\\)

B. a[first] and a[last] point to the same variable in the last iteration when cnt is odd. The function inplace_swap xor these two variables however since they point to the same number, the operation evaluates to zero.

C.
```c
    for (first = 0, last=cnt-1;
        first < last;
        first++, last--)
```

# Practice Problem 2.12

A. ```x &= 0xFF```

B. ```x ^= ~0xFF```

C. ```x |= 0xFF``` 

# Practice Problem 2.13

```c
/* Declarations of functions implementing operations bis and bic */
int bis(int x, int m);
int bic(int x, int m);
/* Compute x|y using only calls to functions bis and bic */
int bool_or(int x, int y) {
    int result = bis(x, y);
    return result;
}
/* Compute x^y using only calls to functions bis and bic */
int bool_xor(int x, int y) {
    int result = /* left to reader to solve (I couldn't do it myself) */;
    return result;
}
```

# Practice Problem 2.14

\\(\begin{align} a &= 0101\ 0101 = 0x55\\\ 
                 b &= 0100\ 0110 = 0x46\end{align}\\)

| Expression     | Value | Expression | Value
| --- | ---| ---| ---
|  a  &   b      | 68    | a&&b       | 0x01
|  a  |   b      | 87    | a||b       | 0x01
| ~a  |  ~b      | -71   | !a||!b     | 0x00
|  a  &  !b      | -71   | a&&~b      | 0x01

Skipped to Problem 2.45 due to lack of interest and knowing most of the content.

# Practice Problem 2.45

| Fractional value   | Binary representation    | Decimal representation
| --- | ---| --- |
| \\(\frac{1}{8}\\)  | 0.001                    | 0.125
| \\(\frac{3}{4}\\)  | 0.11                     | 0.75
| \\(\frac{5}{16}\\) | 0.0011                   | 0.3125
| ...|...|...

You get the point

# Practice Problem 2.46
A. 

\\(\begin{align}0.1 &= 0.0001\ 1001\ 1001\ 1001\ 1001\ 1001\ [1001]\\\x &= 0.0001\ 1001\ 1001\ 1001\ 1001\ 0100\\\0.1-x &= 0.0000\ 0000\ 0000\ 0000\ 0000\ 0101\ [1001]\end{align}\\)

B.
\\(\begin{align} 0.1-x &= 2^{-22} + 2^{-24} + [(2^{-25} + 2^{-28}) + (2^{-29} + 2^{-32}) + ...] \\\ &= 2^{-22} + 2^{-24} + \sum_{i=0}^{\infty} (2^{-25-4i} + 2^{-28-4i})\\\ &= 2^{-22} + 2^{-24} + \frac{1}{5} \cdot 2^{-32} & \text{Simplify the sum and apply geometric series formula}\\\ &= 2^{-22}(1+2^{-2}+\frac{2^{-10}}{5})\\\ &= 2^{-22}(\frac{6401}{5120}) \\\ &=  2.9806979\cdot 10^{-7}\end{align}\\)

C.

\\(\text{100hr} = 3600000 \cdot \text{0.1s} = 3600000\cdot (0.000110011[0011]\cdots)_2\\\ \\)
\\(3600000\cdot 0.1\text{s} - 3600000\cdot (x)\text{s} = 3600000(0.1\text{s}-(x)s)=3600000\cdot 2.9806979\cdot 10^{-7}\text{s} = 1.073051244\text{s}\\)

D.