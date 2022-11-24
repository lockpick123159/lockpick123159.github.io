---
layout: post
title: "Floor, ceiling techinques"
---

1. Prove \\( n = \lceil n/2 \rceil + \lfloor n/2 \rfloor \\) where \\(n\\) is a nonnegative integer.

We note that \\(k = \lceil n/2 \rceil\\) and \\(m = \lfloor n/2 \rfloor\\) are equivalent to \\(k-1< n/2 \leq k\\) and \\(m \leq n/2 < m+1 \\) respectively.
Since if \\(a\leq b\\) and \\(c < d \\), then \\(a+c < b+d\\), the inequalities show that \\(k+m-1 < n < k+m+1\\). There is only one integer in this interval: \\(m+k = \lceil n/2 \rceil + \lfloor n/2 \rfloor = n\\) since there are \\(\lceil k+m+1 \rceil - \lfloor k+m-1 \rfloor - 1 = k+m\\) many integers in the interval.