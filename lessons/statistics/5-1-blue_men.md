[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

#1. Import data and view the first rows to get a sense of the data and column headers.
import brfss
df = brfss.ReadBrfss()
df.head()
print(df.head())

#2. Filter the data to just include men (only men are qualified for the Blue Man Group)
men = df['sex']==1
dfmen = df[men]
print(dfmen.head())

#3. Add a new column with height converted to inches.
dfmen['hgtinches'] = dfmen['htm3'] * 0.393
print(dfmen.head())

#4. Add the minimum and maximum heights qualified for the Blue Man Group as variables and plot the CDF of height in inches.
minhgt = 71.0
maxhgt = 73.0
cdf = thinkstats2.Cdf(dfmen.hgtinches, label='height inches')
thinkplot.Cdf(cdf)

#5. Calculate the percentile rank of the minimum and maximum qualified heights, and subtract the min from the max to get the percentage of men whose heights would qualify for the Blue Man Group.
min_percentile = cdf.Prob(71)
max_percentile = cdf.Prob(73)
blue_man_group = max_percentile - min_percentile
blue_man_group

#6. Answer: 21.3%
