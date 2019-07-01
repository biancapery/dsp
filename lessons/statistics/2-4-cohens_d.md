[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> REPLACE THIS TEXT WITH YOUR RESPONSE
"""
Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others.

Compute Cohen’s effect size to quantify the difference between the groups. How does it compare to the difference in pregnancy length?
"""

firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()
"first" babies average weight is 7.201094430437772  
"other" babies average weight is 7.325855614973262

CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
Cohen effect size of the weights is -0.088672927072602
Cohen effect size of the pregnancy length is 0.028879044654449883
The effect size of the weights is going in the opposite direction of the effect size of pregnancy length. Either way, they are both extremely small effect sizes. 


