[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```python
import scipy
```

Let's convert everything to centimeters. So the minimum height for a BMG member is 70" = 177.8cm, and the maximum is 73" = 185.42cm.

```python
scipy.stats.norm.cdf(185.42, loc=178, scale=7.7) - scipy.stats.norm.cdf(177.8, loc=178, scale=7.7)
```

This yields 34.27%.
