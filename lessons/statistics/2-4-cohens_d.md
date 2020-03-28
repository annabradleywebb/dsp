[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

#Calculates the mean birthweight of first-born babies and other babies.

totalwgt_first_avg = firsts['totalwgt_lb'].mean()
totalwgt_other_avg = others['totalwgt_lb'].mean()
print('The average weight of first babies is {:.3} lbs and the average weight of other babies is {:.3} lbs. The average weight of other babies is {:.3} lbs greater than first babies.'.format(totalwgt_first_avg,totalwgt_other_avg,(totalwgt_other_avg-totalwgt_first_avg)))

#Calculates Cohen's effect for first-born and other babies.

varfirst = firsts['totalwgt_lb'].var()
varother = others['totalwgt_lb'].var()
n1, n2 = len(firsts['totalwgt_lb']), len(others['totalwgt_lb'])

pooled_var = (n1 * varfirst + n2 * varother) / (n1 + n2)
d = (totalwgt_first_avg-totalwgt_other_avg)/np.sqrt(pooled_var)
print("The difference in means between the average weight of first babies and the average weight of other babies is {:.3} standard deviations, which is very small.".format(d))

#Compares Cohen's effect on pregnancy lengths and sizes for first-born babies.
varfirst = firsts['totalwgt_lb'].var()
varother = others['totalwgt_lb'].var()
n1, n2 = len(firsts['totalwgt_lb']), len(others['totalwgt_lb'])

pooled_var = (n1 * varfirst + n2 * varother) / (n1 + n2)
d = (totalwgt_first_avg-totalwgt_other_avg)/np.sqrt(pooled_var)
print("The difference in means between the average weight of first babies and the average weight of other babies is {:.3} standard deviations, which is very small.".format(d))
