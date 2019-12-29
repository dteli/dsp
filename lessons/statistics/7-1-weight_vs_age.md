[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

I took the agescrn and totalwgt_lb columns out of the dataframe and fed them to the thinkstats2 module's correlation functions.

```python
import thinkstats2
import nsfg

df = nsfg.ReadFemPreg()

awdf = df[['agescrn','totalwgt_lb']].dropna()

p_corr = thinkstats2.Corr(awdf['agescrn'], awdf['totalwgt_lb'])
s_corr = thinkstats2.SpearmanCorr(awdf['agescrn'], awdf['totalwgt_lb'])
```

The Pearson correlation ends up being around .04, the Spearman slightly higher at .042. Neither is an especially notable correlation. This surprised me, I was actually expecting something here.

I inspected the scatterplots for other relationships but didn't seem to find anything.
