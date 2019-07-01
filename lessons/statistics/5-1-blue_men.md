[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters mu = 178 cm and sigma = 7:7 cm for men, and mu = 163 cm and sigma = 7:3 cm for women.

In order to join Blue Man Group, you have to be male between 5'10" and6'1" (see http://bluemancasting.com). What percentage of the U.S. male population is in this range?

import scipy.stats

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
type(dist)
The type is scipy.stats._distn_infrastructure.rv_frozen

dist.mean(), dist.std()
(178.0, 7.7)

dist.cdf(mu-sigma)
0.1586552539314574 - about 16% of people are more than one SD below the mean

low = dist.cdf(177.8)    # 5'10"
high = dist.cdf(185.4)   # 6'1"
low, high, high-low
The output is (0.48963902786483265, 0.8317337108107857, 0.3420946829459531) - about 34% of the population is between 5'10 and 6'1.
