[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```python
from random import random
import pandas as pd
import thinkstats2

random1000 = [random() for x in range(1000)]
# and for fun..
random10000 = [random() for x in range(10000)]
```


```python
pmf1000 = thinkstats2.Pmf(random1000)
pmf10000 = thinkstats2.Pmf(random10000)
cdf1000 = thinkstats2.Cdf(pmf1000)
cdf10000 = thinkstats2.Cdf(pmf10000)
```

WORK IN PROGRESS
