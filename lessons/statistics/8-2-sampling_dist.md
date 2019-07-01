[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

Suppose you draw a sample with size n=10 from an exponential distribution with λ=2. Simulate this experiment 1000 times and plot the sampling distribution of the estimate L. Compute the standard error of the estimate and the 90% confidence interval.

Repeat the experiment with a few different values of n and make a plot of standard error versus n.


def SimulateSample(lam=2, n=10, iters=1000):
   
    def VertLine(x, y=1):
        thinkplot.Plot([x, x], [0, y], color='0.8', linewidth=3)

    estimates = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        lamhat = 1.0 / np.mean(xs)
        estimates.append(lamhat)

    stderr = RMSE(estimates, lam)
    print('standard error', stderr)

    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('confidence interval', ci)
    VertLine(ci[0])
    VertLine(ci[1])

    # plot the CDF
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='estimate',
                     ylabel='CDF',
                     title='Sampling distribution')

    return stderr

SimulateSample()

Output is:
standard error 0.825791904537049
confidence interval (1.311259184670713, 3.7054533946140884)
0.825791904537049

With sample size 10:
standard error 0.762510819389confidence interval (1.2674054394352277, 3.5377353792673705)

As sample size increases, standard error and the width of the CI decrease:

10      0.90    (1.3, 3.9) 
100     0.21    (1.7, 2.4)
1000    0.06    (1.9, 2.1)

All three confidence intervals contain the actual value, 2.

