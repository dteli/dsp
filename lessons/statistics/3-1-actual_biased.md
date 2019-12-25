[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```python
import numpy as np
import pandas as pd
from thinkstats2 import Pmf
import nsfg

df = nsfg.ReadFemResp()
```

The data we want is contained in the 'numkdhh' column, let's do a value count to see what we're dealing with..
```python
numkdhh = df.numkdhh

numkdhh.value_counts()
```

We can feed this to thinkstats' `Pmf` class to create an object.
```python
pmf = Pmf(numkdhh)
```

So we have one pmf. For the other, instead of using `BiasPmf`, I'll just follow the same steps myself. What Allen does is to first copy the pmf so we don't alter the original, then multiply each item by itself (to account for higher probabilities among higher counts, I guess, not sure how to put it) before finally renormalizing the distribution.
```python
pmf_biased = pmf.Copy()

for i in pmf_biased:
  pmf_biased.Mult(i, i)
  
pmf_biased.Normalize()
```
