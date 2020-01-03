[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

I had problems with the code on this one.. but I think I worked through it.

The sample has mean 4.66 and median 4.71.
The skewness is -0.64 and the Pearson's skewness is -0.33. 

If you assume that people make more than a million bucks (let's say a *billion*), which is reasonable, and that the top group is split linearly all the way up, which is probably not reasonable...

OK so instead we'll use linspace for everything except the last bracket, from 5.398 to 9 (instead of 6) on the log scale, and for the last bracket we'll use logspace. This might be way off, I have no idea. Anyway this means using `logspace(df.log_lower[41], df.log_upper[41], df.freq[41])` and then taking `np.log10` of that whole array itemwise.

The mean is now 4.69. The median is still 4.71, so, the same, but that makes sense since we're just changing numbers on the high end without changing the number in the set.
The skewness is now 2.075, which sounds significant? But what is this supposed to measure in the first place? Pearson's is about 0 (-0.081), so, less susceptible to outliers like the book says.
