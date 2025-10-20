# Eksempler på fordelingsfunktioner

## Binomialfordeling

$$
\sum_{t=0}^x \begin{pmatrix}n \\ t \end{pmatrix}p^t(1-p)^{n-1}
$$

## Poissonfordeling

$$
\sum_{n=0}^x \frac{\lambda^d}{n!}e^{-\lambda}
$$

## Geometrisk fordeling

$$
1-1(1-p)^x
$$

## Exponentialfordeling

$$
1-e^{-\lambda x}
$$

## Normalfordeling

$$
\int_{-\infty}^x \frac{1}{\sigma\sqrt{2\pi}}e^{-1\frac{1}{2}\left(\frac{t-\mu}{\sigma}\right)}dt
$$

## Gammafordeling
for $gamma(r, \lambda)$:

$$
1-\sum_{n=0}^{r-1} \frac{(\lambda x)^n}{n!}e^{-\lambda x}
$$
