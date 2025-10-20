# Uafhængige normalfordelte variable

> Uge 9 3/11/23
> 
> Chap. 5.3

### Linearkombination

$$
Z  = aX + bY\\
$$

Hvis:

$$
a^2+b^2=1\implies\\ 
Z\sim N(0,1)
$$

For generelle $a$ og $b$:

$$
Z = \sqrt(a^2+b^2)\left(\frac{a}{\sqrt{(a^2+b^2}}+\frac{b}{\sqrt{(a^2+b^2}}Y\right),\\
Z \sim N(0,a^2+b^2)
$$

Lad en variabel $R$ betegne afstanden fra origo og punktet $(X,Y)$.

Da er 

$$
P(r≤R≤r+dr) \cong f_R(r)dr=c^2e^{\frac{-r^2}{2}}(\pi(r+dr)^2-\pi r^2)\\
c^2e^{\frac{-r^2}{2}}(2\pi r dr + \pi dr^2) = c^22\pi re^{\frac{-r^2}{2}}
$$

$$
1=\int_0^\infty f_R (r)dr \implies c = \frac{1}{\sqrt{2\pi}}
$$

### Rayleighfordelingen

$$
f_R(r)=re^{-\frac{1}{2}r^2},\\
P(R≤r)=F_R(r)=1-e^{-\frac{1}{2}r^2}
$$

### ...

$$
X, Y \sim N(0,1), \text{Uafhængige}
$$

$$
R = \sqrt{X^2+Y^2}, P(R≤r) = F_R(r)
$$

$$
S=R^2=X^2+Y^2
$$

$$
F_S(s)=P(S≤s)=P(R^2≤s)=P(R≤\sqrt{s})
$$

$$
P(S≤s)=P(R≤\sqrt{s})=1-e^{-\frac{1}{2}s}
$$

$$
S \sim exp\left(\frac{1}{2}\right)E(S)=2
$$
