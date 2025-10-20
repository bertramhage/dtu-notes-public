---
Uge: Uge 9 - 3/11/23
Pensum: Kap. 5.4
tags:
  - kontinuerte
  - variable
  - sum
  - max
  - chi2
---
# Operationer med stokastiske variable

### Tætheder for kontinuerte variable

For uafhængige diskrete variable har vi tidligere set 

$$
P(Z=X+Y=z) = \sum_{x=-\infty}^\infty f_X(x)f_Y(z-x)
$$

For kontinuerte tætheder får vi

$$
f_Z(z) = \int_{-\infty}^\infty f(x,z-x)dx =_{uaf} \int_{-\infty}^\infty
f_X(x)f_y(z-x)dx
$$

##### Eksempel

Lad $X1$ være ligeligt fordelt på enhedsintervallet og $X2$ være ligeligt
fordelt på intervallet $(0,2)$ og uafhængig af $X1$.

Find tætheden $f_Z(z)$ for $Z = X_1 + X_2$

$$
\delta_{(cond)}=\begin{cases}1, cond:T\\0, cond:F\end{cases}
$$

$$
f(x,y)=f_X(x)f_Y(y)=\delta_{(0<x<1)}\frac{1}{2}\delta_{(0<y<2)}
$$

$$
f_Z(z) = \int_{-\infty}^\infty \delta_{(0<x<1)}\frac{1}{2}\delta_{(0<z-x<2)}dx
$$

$$
\implies
\begin{cases}
\int_0^z 1 \frac{1}{2}dx = \frac{z}{2},         0<z≤1\\
\int_0^1 1 \frac{1}{2}dx = \frac{1}{2},         1<z≤2\\
\int_{z-2}^{1} 1 \frac{1}{2}dx = \frac{3-z}{2}, 2<z<3
\end{cases}
$$

### Sum af max og min af to exp fordelte variable

Vi har tidligere set at for $W_i\in exp(\lambda), X=min(W_1, W_2)$ og $Y=min(W_1, W_2)$ er den simultane tæthed:

$$
f(x,y)=2\lambda^2 e^{-\lambda(x+y)}, 0<x≤y.
$$

Fordelingen af $Z=X+Y$ findes til

$$
f_Z(z) = \int_0^{\frac{x}{2}} 2\lambda^2 e^{-\lambda(x+(z-x))}dx = \lambda(\lambda z)e^{-\lambda z}
$$

### Summer af uafhængige variable

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_lv2ECc/Skærmbillede%202023-11-03%20kl.%2011.43.07.png" alt="Skærmbillede 2023-11-03 kl. 11.43.07.png" data-align="center" width="371">

### $\chi^2$-fordelingen

Summer af kvadrerede uafhænige standard normalfordelte variable

$X_i \sim normal(0,1)$, uafhængige. Da har $Y=\sum_{i=1}^n X_i^2$ tæthed

$$
f_Y(y) = \frac{1}{2^{n/2}\Gamma(n/2)}y^{(n/2)-1}e^{-y/2}
$$

.. og siges at være $\chi^2$-fordelt med $n$ frihedsgrader.

(Det er også en Gamma-fordeling $\Gamma(n/2, 1/2)$)

Reproduktion: Hvis $Y_1 \sim \chi^2(n)$ og $Y_2 \sim \chi^2(m)$, så er $Y_1 + Y_2 \sim \chi^2(n+m)$.

### Fordeling af forhold

Hvis $Z=\frac{Y}{X}$, hvor $X$ og $Y$ er uafhængige er

$$
f_Z(z) = \int_{-\infty}^\infty |x|f_X(x)f_Y(xz)dx
$$



##### Eksempel

Spm: Find tætheden af $Y = \frac{V}{U}$, hvor $U$ og $V$ er uafhængige ligefordelte $(0,1)$ variable.

Svar:

$$
f(u,v) = 1 \delta_{(0<u<1)}\delta_{(0<v<1)}
$$

$$
f_Y(y) = \int_{-\infty}^\infty |u| \delta_{(0<u<1)}\delta_{(0<uy<1)}du
$$

$$
\implies 0<u \land u< 1 \land 0<uy \land uy < 1 \Leftrightarrow \\
0<u \land u<1 \land 0<u \land u < \frac{1}{y}
$$

Nedre grænse: $max(0,0)$

Øvre grænse: $min(1, \frac{1}{y})$

$$
f_Y(y) = \int_{-\infty}^\infty |u| \delta_{(0<u<1)}\delta_{(0<u<\frac{1}{y})}du
$$

$$
= \int_{-\infty}^0 + \int_0^1 + \int_1^\infty
$$

$$
=\begin{cases}
\int_0^1 u du = \left[\frac{1}{2}u\right]_0^1 = \frac{1}{2}, y<1\\
\int_0^{\frac{1}{y}} u du = \frac{1}{2y^2}, 1<y
\end{cases}
$$


