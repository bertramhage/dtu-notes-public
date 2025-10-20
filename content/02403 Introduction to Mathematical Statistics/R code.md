## Summary statistics
``` R
# Sample mean
mean(x)
```

```R
# Sample median
median(x)
```

``` R
# Sample variance
var(x)
```

``` R
# Sample standard deviation
sd(x)
```

``` R
# Sample quartiles
quantile(x, type=2)
```

## Probability
``` R
# Sum of vector
sum(x)
```

``` R
# Binomial (WITH replacement)
# N number of trial
# p probability of success for each trial
# x number of successes
dbinom(x, N, p)
```

``` R
# Hyper geometric (WITHOUT replacement)
# N number of balls in total
# G number of white balls
# n number of draws
# g number of white balls drawn
dhyper(g, G, N-G, n)
```

## Statistics for one and two samples
``` R
# Confidence interval for difference in mean from two samples by t-test
A <- c(8.360, 6.377,  7.385, 6.245, 8.766, 6.848, 6.074, 6.310, 5.946, 8.270)
B <- c(8.806, 6.513, 10.209, 5.495, 6.513, 8.529, 8.354, 5.681, 7.553, 6.834)
t.test(A,B,conf.level = 0.975)
# Response
	# 	Welch Two Sample t-test
	#
	# data:  A and B
	# t = -0.66931, df = 16.139, p-value = 0.5128
	# alternative hypothesis: true difference in means is # not equal to 0
	# 97.5 percent confidence interval:
	#  -1.832454  1.051254
	# sample estimates:
	# mean of x mean of y 
	#    7.0581    7.4487 
```
## Inference for Proportions
``` R
# Prop test
# prop.test can be used for testing the null that the proportions (probabilities of success) in several groups are the same, or that they equal certain given values.
s <- c(178,212)
n <- c(706,885)
prop.test(s, n, correct=FALSE)
# Response
	# 2-sample test for equality of proportions
	# without continuity correction
	
	# data:  c(178, 212) out of c(706, 885)
	# X-squared = 0.33569, df = 1, p-value =
	# 0.5623
	# alternative hypothesis: two.sided
	# 95 percent confidence interval:
	# -0.03004594  0.05519919
	# sample estimates:
	#   prop 1    prop 2 
	# 0.2521246 0.2395480 
```

``` R
# Test of nullhypothesis with t-test
# H0: mu = mu0
# With observed mean mu, observed sd sigma, sample size n
tobs <- (mu - mu0) / (sigma / sqrt(n))

# Compute the p-value as a tail-probability in the t-distribution
pvalue <- 2 * (1-pt(abs(tobs), df=n-1))
```

``` R
# The (1-alpha/2) quantile from the t-distribution with n-1 df
qt(1-alpha/2, df=n-1)
```

``` R
# Chisq test from matrix where r=c=3
# df = (r-1)(c-1)
data <- matrix(c(79, 91, 93, 84, 66, 60, 37, 43, 47), ncol = 3)
chisq.test(data)
# Response
	#	Pearson's Chi-squared test
	
	# data:  matrix(c(79, 91, 93, 84, 66, 60, 37, 43, 47), ncol = 3)
	# X-squared = 10.985, df = 4, p-value = 0.02673
```
## Anova
``` R
y <- c(2.8, 3.6, 3.4, 2.3,
       5.5, 6.3, 6.1, 5.7,
       5.8, 8.3, 6.9, 6.1)

treatm <- factor(c(1, 1, 1, 1,
                   2, 2, 2, 2,
                   3, 3, 3, 3))

anova(lm(y ~ treatm))
# Response
	# Analysis of Variance Table
	# Response: y
	
	#           Df Sum Sq Mean Sq F value  Pr(>F)
	# treatm     2   30.8   15.40    26.7 0.00017 ***
	# Residuals  9    5.2    0.58
	# ---
	# Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

``` R
# Critical value for F statistic
# df2: df for residuals
qf(0.95,df1=1,df2=2)
## [1] 18.51282
```

``` R
# P value given F statistic
F_stat = 2.2731
df1 = 6 #df for treatment
df2 = 18 #df for residuals
pvalue = 1-pf(F_stat, df1, df2)
```

