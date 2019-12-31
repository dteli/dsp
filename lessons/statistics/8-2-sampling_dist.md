[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

```python
import numpy as np
from scipy.stats import expon
import thinkstats2

def get_est_Ls(n=10, m=1000, lam=2):
    return [1/(np.mean(xs)) for xs in [[expon.rvs(loc=0, scale=lam) for _ in range(n)] for _ in range(m)]]
    

est_Ls = get_est_Ls()

est_Ls_100 = get_est_Ls(n=100)

```

I'm not sure I'm doing this right. It sounds like the confidence range is just the range from the low-end percentile to the high-end, so for n=10 and 100:

```python
percentiles_10 = np.percentiles(est_Ls, [5, 95])
percentiles_100 = np.percentiles(est_Ls_100, [5, 95])
```

For standard error, it sounds like we're required to know the type and parameters of the distribution, which we *do*, but that doesn't mean we always will, so I'm confused.

```python
# borrowing his RMSE function from Think Stats
def RMSE(estimates, actual):
  e2 = [(estimate-actual)**2 for estimate in estimates]
  mse = np.mean(e2)
  return math.sqrt(mse)

# here we assume we used lam=2 above
error_10 = RMSE(est_Ls, 0.5)
error_100 = RMSE(est_Ls_100, 0.5)
```

For error_10 I get .21 and for error_100 I get .05.
