[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```
from math import sqrt
import numpy as np
import pandas as pd
import nsfg

df = nsfg.ReadFemPreg()

# mostly taking this from functions in the book
live = df[df.outcome == 1]
first = live[live.birthord == 1]
other = live[live.birthord != 1]

n_first = len(first)
n_other = len(other)

var_first_wgt = first.totalwgt_lb.var()
var_other_wgt = other.totalwgt_lb.var()

pooled_var = (n_first * var_first_wgt + n_other * var_other_wgt) / (n_first + n_other)

d = (first.totalwgt_lb.mean() - other.totalwgt_lb.mean()) / sqrt(pooled_var)
```

Here I get d ≈ -0.089, which seems to be a greater effect than that between the groups on birth week,
but still it's a small effect.

d is negative, so the first births tend to be lighter.
