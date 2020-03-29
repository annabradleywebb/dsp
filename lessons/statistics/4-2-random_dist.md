[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

# Random numpy numbers
random_thousand = np.random.random(1000)
# Plotting PMF of the random numbers
pmf = thinkstats2.Pmf(random_thousand, label='actual')
thinkplot.Pmf(pmf)
#The values all have the same probability, so the PMF is just a big rectangle (all values have a probability of 1).
# Plotting CDF of random numbers
cdf = thinkstats2.Cdf(random_thousand, label='actual')
thinkplot.Cdf(cdf)
The CDF is a straight line, so the distribution is normal (which is expected because all values are equally likely with the random tool).