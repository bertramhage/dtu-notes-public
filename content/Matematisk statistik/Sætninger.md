## Summary statistics
>[!info] Sample mean
>Sample mean is the sum of observations divided by the number of observations
>$$
>\bar{x}=\frac{1}{n}\sum_{i=1}^{n} x_i \, 
>$$

>[!info] Median
>Order the $n$ ovservations $x_{1}, \dots, x_n$ from the smallest to largest: $x_{(1)}, \dots, x_{(n)}$. The median is defined as:
>If $n$ is odd:
>$$
>Q_2=x_{\left( \frac{n+1}{2} \right)}
>$$
>If $n$ is even:
>$$
>Q_2=\frac{x_{(\frac{n}{2})}+x_{\left( \frac{n+2}{2} \right)}}{2}.
>$$

>[!info] Quantiles and percentiles
>The $p$ quantile can be defined by
>1. Order the $n$ observations from smallest to largest: $x_{(1)}, \dots, x_{(n)}$
>2. Compute $pn$
>3. If $pn$ is an integer: average the $pn'$th and $(pn+1)$'th ordered observations. Then the $p$ quantile is
>$$
>q_p=\frac{x_{(np)}+x_{(np+1)}}{2}
>$$
>4. If $pn$ is a non-integer: take the "next one" in the ordered list. Then the $q$'th quantile is
>$$
>q_p=x_{(\lceil np \rceil )}.
>$$

>[!info] Sample variance and standard deviation
>The sample variance of a sample $x_{1},\dots, x_n$ is given by
>$$
>s^2=\frac{1}{n-1}\sum_{i=1}^{n} (x_i-\bar{x})^2. \, 
>$$
>The sample standard deviation is given by
>$$
>s=\sqrt{ s^2 }=\sqrt{ \frac{1}{n-1}\sum_{i=1}^{n} (x_i-\bar{x})^2 \,  }.
>$$

>[!info] Sample covariance
>The sample covariance is
>$$
>s_{xy}=\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})(y_i-\bar{y}).  \, 
>$$

>[!info] Sample correlation
>The sample correlation coefficient is
>$$
>r=\frac{1}{n-1}\sum_{i=1}^{n} \left( \frac{x_i-\bar{x}}{s_x} \right)\left( \frac{y_i-\bar{y}}{s_y} \right)=\frac{s_{xy}}{s_{x}\cdot s_y}, \, 
>$$
>where $s_x$ and $s_y$ is the sample standard deviation for $x$ and $y$ respectively.

## Probability
#### Discrete random variables
>[!info] The $pdf$ and $cdf$ of a discrete random variable
>For a discrete random variable $X$ the $pdf$ is
>$$
>f(x)=P(X=x),
>$$
>where
>$$
>f(x)≥0 \forall x\text{ and }\sum_{\text{all }x}f(x)=1.
>$$
>The $cdf$ for the discrete case is
>$$
>F(x)=P(X≤x)= \sum_{j, x_j≤x}f(x_j)=\sum_{j, x_j≤x}P(X=x_j).
>$$

>[!info] Mean value
>The mean of a discrete random variable $X$ is
>$$
>\mu=E(X)=\sum_{j=1}^{\infty} x_jf(x_j), \, 
>$$
>where $x_j$ is the value and $f(x_j)$ is the probability that $X$ takes the outcome value $x_j$.

>[!info] Variance
>The variance of a discrete random variable $X$ is
>$$
>\sigma^2=V(X)=E[(X-\mu)^2]=\sum_{i=1}^{\infty} (x_j-\mu)^2f(x_j), \, 
>$$
>where $x_j$ is the outcome value and $f(x_j)$ is the $pdf$ of the $i$th outcome value.

>[!info] Expected value for linear combinations
>Let $X$ be a random variable and $a$ and $b$ constants. Then
>$$
>E(aX+b)=aE(X)+b
>$$

>[!info] Variance for linear combinations
>Let $X$ be a random variable and $a$ and $b$ constants. Then
>$$
>Var(aX+b)=a^2Var(X) \implies
>$$
>$$
>SD(aX+b)=|a|SD(X)
>$$

>[!info] Covariance between linear combinations
>Let $X$ and $Y$ be two random variables, then
>$$
>Cov(a_{0}+a_{1}X+a_{2}Y, b_{0}+b_{1}X+b_{2}Y)=a_{1}b_{1}V(X)+a_{2}b_{2}V(Y)+(a_{1}b_{2}+a_{2}b_{1})Cov(X,Y)
>$$
#### Discrete distributions

>[!info] Binomial distribution
>For $X\sim B(n,p)$, where $n$ is the number of independent draws and $p$ is the probability of a success in each draw.
>The $pdf$ for $x$ successes is
>$$
>f(x;n,p)=P(X=x)=\begin{pmatrix}n\\ x\end{pmatrix}p^x(1-p)^{n-x}.
>$$

## Statistics for one and two samples
>[!info] Distribution of the mean of normal random variables
>Assume that $X_{1}, \dots, X_n$ are independent and identically normally distributed random variables, $X_i\sim N(\mu, \sigma^2), i=1,\dots, n$, then
>$$
>\bar{X}=\frac{1}{n}\sum_{i=1}^{n} X_i\sim N\left( \mu, \frac{\sigma^2}{n} \right) \,. 
>$$

>[!info] Distribution of the $\sigma$-standardized mean of normal random variables
>Assume that $X_{1}, \dots, X_n$ are independent and identically normally distributed random variables, $X_i\sim N(\mu, \sigma^2)$ where $i=1,\dots, n$, then
>$$
>Z = \frac{\bar{X}-\mu}{\frac{\sigma}{\sqrt{ n }}}\sim N(0,1^2).
>$$

>[!info] Method: One sample confidence interval for $\mu$
>For a sample $x_{1}, \dots, x_n$ the $100(1-\alpha)\%$ confidence interval is given by
>$$
>\bar{x}\pm t_{1-\alpha/2}\cdot \frac{s}{\sqrt{ n }},
>$$
>where $t_{1-\alpha/2}$ is the $(1-\alpha/2)$ quantile from the t-distribution with $n-1$ degrees of freedom.

>[!info] Method: Two-sample confidence interval for $\mu_{1}-\mu_{2}$
>For two samples $x_{1}, \dots, x_n$ and $y_{1}, \dots, y_n$ the $100(1-\alpha)\%$ confidence interval for $\mu_{1}-\mu_{2}$ is given by
>$$
>\bar{x}-\bar{y}\pm t_{1-\alpha/2}\cdot \sqrt{ \frac{s_{1}^2}{n_{1}} + \frac{s_{2}^2}{n_{2}}},
>$$
>where $t_{1-\alpha/2}$ is the $(1-\alpha/2)$-quantile from the $t$-distribution with $v$ degrees of freedom given by
>$$
>v=\frac{\left( \frac{s_{1}^2}{n_{1}}+\frac{s_{2}^2}{n_{2}} \right)^2}{\frac{(s_1^2/n_{1})^2}{n_{1}-1}+\frac{(s_{2}^2/n2)^2}{n_{2}-1}}
>$$

>[!info] Method: Confidence interval for the variance/standard deviation
>A $100(1-\alpha)\%$ confidence interval for the variance $\sigma^2$ is
>$$
>\left[ \frac{(n-1)s^2}{\chi^2_{1-\alpha/2}}, \frac{(n-1)s^2}{\chi^2_{\alpha/2}} \right]
>$$
>where $v=n-1$.
>A $100(1-\alpha)\%$ confidence interval for the variance $\sigma$ is
>$$
>\left[\sqrt{  \frac{(n-1)s^2}{\chi^2_{1-\alpha/2}}},\sqrt{   \frac{(n-1)s^2}{\chi^2_{\alpha/2}}} \right]
>$$

>[!info] Method 3.65: The one-sample sample size formula
>For the one-sample $t$-test for given $\alpha, \beta$ and $\sigma$
>$$
>n = \left( \sigma \frac{z_{1-\beta}+z_{1-\alpha/2}}{(\mu_{0}-\mu_{1})} \right)^2
>$$
>where $\mu_{0}-\mu_{1}$ is the difference in means that we would want to detect and $z_{1-\beta}, z_{1-\alpha/2}$ are quantiles of the standard normal distribution.

## Linear regression
>[!info] Degrees of freedom
>Let $n$ be number of observations and $p$ be number of variables in a linear model
>$$
>Y_i=\beta_{0}+\beta_{1}x_{1,i}+\dots+\beta_px_{p,i}+\epsilon_i, \epsilon \sim N(0,\sigma^2)
>$$
>then the degrees of freedom is
>$$
>v = n - (p-1).
>$$

#### Matrix form
>[!info] For a linear model
>$$
>\mathbf{Y}=\mathbf{X}\mathbf{\beta}+\mathbf{\epsilon}, \mathbf{e}\sim N(\mathbf{0}, \sigma^2\mathbf{I})
>$$
>the standard errors can be calculated by
>$$
>SE_i=\hat{\sigma}\sqrt{ (\mathbf{X}^T\mathbf{X})_{ii}^{-1} } \Leftrightarrow 
>$$
>$$
>(\mathbf{X}^T\mathbf{X})_{ii}^{-1}=\frac{SE_i^2}{\hat{\sigma}^2}.
>$$
## Inference for Proportions
>[!info] Expected value of cells in multi-sample proportions $\chi^2$-test
>For cell in the $i$'th row and $j$'the column the expected value is
>$$
>e_{ij}=\frac{tot_i\cdot tot_j}{tot},
>$$
>where $tot_i$ is the total of row $i$, $tot_j$ is the total of colum $j$ and $tot$ is the grand total.

>[!info] Method: Proportion estimate and confidence interval
>The best estimate of the probability $p$ of belonging to a category is the sample proportion
>$$
>\hat{p} = \frac{x}{n},
>$$
>where $x$ is the number of observations in the category and $n$ is the total number of observations. 
>A large sample $(1-\alpha)100\%$ confidence interval for $p$ is given as
>$$
>\hat{p}\pm z_{1-\alpha/2}\sqrt{ \frac{\hat{p}(1-\hat{p})}{n} }.
>$$

## ANOVA
>[!info] Under 
>$$
>H_{0}:\alpha i=0, i=1,2,\dots,k
>$$
>the test statistic
>$$
>F=\frac{SS(Tr)/(k-1)}{SSE/(n-k)}
>$$
>follows an $F$-distribution with $k-1$ and $n-k$ degrees of freedom.

>[!info] Method: Post hoc pairwise confidence intervals
>A single pre-planned $(1 − \alpha) · 100\%$ confidence interval for the difference between treatment $i$ and $j$ is found as
>$$
>\bar{y_i}-\bar{y_j}\pm t_{1-\alpha/2}\sqrt{ MSE\left( \frac{1}{n_i}+\frac{1}{n_j} \right) }.
>$$

>[!info] Total variance explained
>The sum of variance $SST$ is given by
>$$
>SST = SS(Tr)+SSE.
>$$
>
>The amount of total variance that is explained by the model is 
>$$
>\frac{SS(Tr)}{SST}=\frac{SS(Tr)}{SS(Tr)+SSE}.
>$$

