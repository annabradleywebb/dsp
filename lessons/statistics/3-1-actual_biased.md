[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

# unbiased pmf of children in a family
children = resp['numkdhh']
pmf = thinkstats2.Pmf(children, label='actual')
print('mean', pmf_children.Mean())

def BiasPmf(pmf_children, label):
    new_pmf_children = pmf_children.Copy(label=label)
    for x,p in pmf_children.Items():
        new_pmf_children.Mult(x,x)
    new_pmf_children.Normalize()
    return new_pmf_children, new_pmf_children.Mean()
bias_children(pmf_children, 'observed')

# plot of unbiased and biased
biased_pmf = BiasPmf(pmf, label='observed')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Show(xlabel='class size', ylabel='PMF')
