## Differentialligninger

#### Form:

##### Homogen

$$
a_{0} \frac{d^ny}{dt^n} + a_{1} \frac{d^{n-1}y}{dt^{n-1}} + \dots +a_{n-1} \frac{dy}{dt}+a_ny=0,
$$

hvor $a_{0}\neq 0, a_{0}, \dots, a_n\in\mathbb{R}$.

##### Inhomogen

$$
a_{0} \frac{d^ny}{dt^n} + a_{1} \frac{d^{n-1}y}{dt^{n-1}} + \dots +a_{n-1} \frac{dy}{dt}+a_ny=u(t),
$$

hvor $a_{0}\neq 0, a_{0}, \dots, a_n\in\mathbb{R},$ og $u$ er en kontinuert funktion med reelle el. komplekse værdier.

#### Løsninger

> [!info] Karakteristiske polynomium
> $$
> a_{0}\lambda^n+a_{1}\lambda^{n-1}+\dots+a_{n-1}\lambda+a_n=0
> $$

> [!info] 1.14 Lin. uaf. løsninger udfra $\lambda$, hvor am($\lambda$)$≥1$
> Lad $\lambda$ være en rod i karakterligningen med am = $\rho$. Da har den homogene differentialligning de lineært uafhængige løsninger
> $$
> y_{1}(t)=e^{\lambda t} , y_{2}(t)=te^{\lambda t}, \dots, y_p(t)=t^{\rho-1}e^{\lambda t}
> $$

> [!info] 1.8 Reelle løsninger
> Hvis $y(t)=Re(y(t)) + iIm(t)$ er løsning til (H) er også $Re(y(t))$ og $Im(y(t))$ løsninger.
> Dsv, givet $\lambda=a+i\omega$, $P(\lambda)=0\Leftrightarrow P(\bar{\lambda})=0$
> $$
> y(t)=c\cdot e^{\lambda t}=c\cdot e^{(a+i\omega)t}=c\cdot e^{at}(\cos(\omega t) + \sin(\omega t)), c\in\mathbb{C}
> $$
> $$
> Re(y(t)) = c_{1}\cdot e^{at}\cos(\omega t), Im(y(t)) = c_{2}\cdot e^{at}\sin(\omega t), c_{1},c_{2}\in\mathbb{R}
> $$

> [!info] 1.20 Struktursætningen
> Den fuldstændige løsning til en inhomogent differentialligning er
> $$
> y(t)=y_0(t) + y_{hom}(t),
> $$
> hvor $y_0(t)$ er en partikulær løsning til den inhomogene differentialligning, og $y_{hom}(t)$ er den fuldstændige løsning til den tilsvarende homogene differentialligning.
<div style="page-break-after: always;"></div>

#### Overføringsfunktionen

> [!info] Overføringsfunktionen (del er fra 1.25)
> For en inhomogen diff ligning:
> $$
> a_{0}y^{(n)}+a_{1}y^{(n-1)}+\dots+a_{n-1}y^{(1)}+a_ny=b_{1}u^{(m)}+\dots+b_{m-1}u^{(1)} + b_m u
> $$
> $$
> H(s)=\frac{b_{1}s^{m}+b_2s^{m-1}+\dots+b_{m-1}s+b_m}{a_{0}s^n+a_{1}s^{n-1}+\dots+a_{n-1}s+a_n}
> $$
> Hvis $u(t)=e^{st}, s \in\mathbb{C}$  er den stationære løsning
> $$
> y(t)=H(s)e^{st}
> $$
> hvis og kun hvis $P(s)\neq 0$.
> 
> Hvis $P=0$ er $ce^{st}$ løsning til den tilsvarende homogene ligning og gættet fejler. Gæt i stedet på $cte^{st}$.
> 
> Hvis $u(t)=c\cdot e^{st}, s \in\mathbb{C}, c\in\mathbb{R}$  er den stationære løsning
> $$
> y(t)=H(s)\cdot c\cdot e^{st}, c\in\mathbb{R}.
> $$

## Systemer af differentialligninger

#### Form:

$$
\begin{align}
\dot{x}_1 = a_{11}x_{1} + a_{12}x_{2} + \dots + a_{1n}x_n+u_1(t) \\
\dots \\
\dot{x}_n = a_{n1}x_{1}+a_{n2}x_{2}+ \dots + a_{nn}x_n+u_n(t) 
\end{align}
$$

##### Matrixform:

$$
\dot{\mathbf{x}} = \mathbf{A}\mathbf{x}+\mathbf{u}(t), \text{hvor }\mathbf{x} \in \mathbb{R}^n, \mathbf{A} \in \mathbb{R}^{n\times n}, \mathbf{u} \in \mathbb{R} ^n
$$

#### Fra $n$'te grads til system
>[!info] 2.2 Omskrivning af $n$'te grads differentiallignings til 1'ste grads system af differentialligninger
>Betragt en $n$'te ordens differentialligning
>$$
>y^{(n)}(t)+b_{1}y^{(n-1)}(t)+\dots+b_{n-1}y'(t)+b_ny(t)=u(t).
>$$
>Vi indfører et sæt af nye variable $x_{1}, x_{2}, \dots, x_n$ ved at sætte
>$$
>x_{1}(t)=y(t), x_{2}(t)=y'(t), \dots, x_n(t)=y^{(n-1)}(t).
>$$
>Da er
>$$
>\begin{cases}
>\dot{x}_1(t)=x_{2}(t),\\
>\cdot \\
>\cdot  \\
>\dot{x}_{n-1}(t)=x_n(t), \\
>\dot{x}_n(t)=-b_nx_{1}(t)-b_{n-1}x_{2}(t)-\dots-b_{1}x_n(t)+u(t)
\end{cases}
>$$
>som på matrixform kan skrives
>$$
>\begin{pmatrix}\dot{x}_1(t)\\\dot{x}_2(t)\\ \cdot \\\cdot \\\dot{x}_{n-1}(t)\\\dot{x}_n(t)\end{pmatrix}
>=
>\begin{pmatrix}0 & 1 & 0 & \cdot  & 0 & 0\\0 & 0 & 1 & \cdot  & 0 & 0 \\ \cdot  & \cdot  & \cdot  & \cdot  & \cdot  & \cdot \\\cdot  & \cdot  & \cdot  & \cdot  & \cdot  & \cdot \\0 & 0 & 0 & \cdot  & 0 & 1\\-b_n & -b_{n-1} & -b_{n-2} & \cdot  & -b_{2} & -b_{1}\end{pmatrix}
>\begin{pmatrix}x_{1}(t)\\x_{2}(t)\\\cdot \\\cdot \\x_{n-1}(t)\\x_n(t)\end{pmatrix}+\begin{pmatrix}0\\0\\\cdot \\\cdot \\0\\1\end{pmatrix}u(t).
>$$

#### Løsninger

> [!info] 2.7 Egenværdimetoden (når am=1)
> Et sæt relle løsninger til den homogene ligning $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$ bestemmes på flg. måde
> (a) For hver reel egenværdi, med tilhørende reel og egentlig egenvektor $\mathbf{v}$ opskrives løsningen
> $$
> \mathbf{x}(t)=e^{\lambda t}\mathbf{v}.
> $$
> 
> (b) Komplekse egenværdier optræder i par $a \pm i\omega$. Vælg en egentlig egenvektor $v$ hørende til egenværdien $\lambda=a+ i\omega$ og opskriv løsningerne
> $$
> \mathbf{x}(t)=Re(e^{\lambda t}\mathbf{v}) = e^{at}(\cos\omega t Re(\mathbf{v}) - \sin\omega t Im(\mathbf{v}))
> $$
> og
> $$
> \mathbf{x}(t)=Im(e^{\lambda t}\mathbf{v})=e^{at}(\sin\omega t Re(\mathbf{v}) + \cos\omega t Im(\mathbf{v})).
> $$

> [!info] 2.11 Løsninger ved multiplicitet $\rho$ (når am>1)
> (a) For hver egenværdi $\lambda$ med am $= \rho$ findes vektorer $\mathbf{b}_{jk}\in \mathbb{R} ^n$ så:
> $$
> \mathbf{x}_1(t) = \mathbf{b}_{11} e^{\lambda t} $$
> $$\mathbf{x}_2(t) = \mathbf{b}_{21}e^{\lambda t} + \mathbf{b}_{22}te^{\lambda t}$$
> $$\dots $$
> $$\mathbf{x}_p(t) = \mathbf{b}_{p1}e^{\lambda t} + \mathbf{b}_{p2}te^{\lambda t} + \dots + \mathbf{b}_{pp}t^{p-1}e^{\lambda t}
> $$
> 
> (b) Antag, at $a\pm i\omega$ er et par komplekst konjugerede egenværdier med am $p≥2$ og gm $q<p$. Lad $\lambda:=a\pm i\omega$. Da findes vektorer $\mathbf{b}_{jk}\in\mathbb{C}$ således at 
> $$
> \begin{align}
> \mathbf{x_1}(t)&=Re(\mathbf{b_{11}}e^{\lambda t}) \\
> \mathbf{x_{2}}(t) &= Re(\mathbf{b}_{21}e^{\lambda t}+\mathbf{b}_{22}te^{\lambda t}) \\
> \cdot  \\
> \cdot  \\
> \mathbf{x_p}(t)&=Re(\mathbf{b}_{p1}e^{\lambda t}+\mathbf{b}_{p2}te^{\lambda t} + \dots+\mathbf{b}_{pp}t^{p-1}e^{\lambda t}) \\
> \mathbf{x_{p+1}}(t)&=Im(\mathbf{b}_{11}e^{\lambda t}) \\
> \mathbf{x_{p+2}}(t)&=Im(\mathbf{b}_{21}e^{\lambda t}+\mathbf{b}_{22}te^{\lambda t}) \\
> \cdot  \\
> \cdot  \\
> \mathbf{x_{2p}}(t)&=Im(\mathbf{b}_{p1}e^{\lambda t}+\mathbf{b}_{p_{2}}te^{\lambda t}+\dots+\mathbf{b}_{pp}t^{p-1}e^{\lambda t})
> \end{align}
> $$
> er lineært uafhængige reelle løsninger til systemet $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$.

> [!info] 2.12 Fuldstændige reelle løsning efter 2.7 og 2.11
> Den fuldstændige reelle løsning til det homogene differentialligningssystem $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$ kan bestemmes på flg. måde:
> 
> 1. For hver reel egenværdi $\lambda$ opskrives løsningerne i 2.7(a)/2.11(a).
> 2. For hvert par $a\pm i\omega$ af komplekst konjugerede egenværdier opskrives løsningerne i sætning 2.7(b)/2.11(b).
> 
> Den fuldstændige reelle løsning til differentialligningssystemet fås ved at danne linearkombinationer af de fundne $n$ løsninger, med reelle koefficienter.

#### Fundamentalmatricen

> [!info] 2.14 Fundamentalmatricen
> Til ethvert sæt af $n$ lin. uaf. løsninger $\mathbf{x}_1(t), \mathbf{x}_{2}(t), \dots, \mathbf{x}_n(t)$ til det hom. system $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$ knyttes en $n\times n$ fundamentalmatrix:
> $$
> \mathbf{\Phi}(t):=[\mathbf{x}_1(t), \mathbf{x}_{2}(t), \dots, \mathbf{x}_n(t)]
> $$
> Søjlerne i $\mathbf{\Phi}(t)$ består altså af vektorerne $\mathbf{x}_i(t),i=1,..,n$.
> 
> Der gælder at $\det(\Phi)\neq 0$.

#### Overføringsfunktioner

> [!info] Overføringsfunktion for et system af diff. lign.
> Betragt systemet
> $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}+\mathbf{u}(t), \mathbf{u}(t)=\mathbf{b}u(t)$
> $y=d_{1}x_{1}+d_{2}x_{2}+\dots+d_nx_n=\mathbf{d}^\top\mathbf{x}$
> Da er 
> $$
> y = H(s)e^{st}
> $$ 
> hvor
> $$
> H(s)=-\mathbf{d}^\top(\mathbf{A}-s\mathbf{I})^{-1}\mathbf{b}e^{st}
> $$

#### Stabilitet

> [!info] 2.28 $(i)$ Stabilitet (marginal stabilitet)
> Det homogene system $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$ siges at være stabilt, hvis enhver løsning $\mathbf{x}(t), t \in [t_{0}, \infty[$ er begrænset.
> Dvs. at der findes en konstant $k>0$ så $$|| \mathbf{x}(t)||=(|x_{1}(t)|^2 + \dots+|x_n(t)^{2})^{\frac{1}{2}}<k$$

> [!info] 2.38 Asymptotisk stabilitet
> Det homogene system $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$ siges at være asymptotisk stabilit hvis og kun hvis alle egenværdier for $\mathbf{A}$ har negativ realdel.

> [!info] 2.41 Routh-Hurwitz kriterium
> Givet et polynomium med reelle koefficienter, på formen
> $$
> P(\lambda) = \lambda^n+a_{1}\lambda^{n-1} + \dots + a_{n-1}\lambda+a_n
> $$
> har alle rødder negativ realdel hvis og kun hvis de flg to kriterier er opfyldt:
> 
> 1. Alle koefficienterne er positive, dvs $a_k>0$ for $k=1,\dots,n$.
> 2. Alle $k\times k$ determinanter, $k=2,\dots,n-1$, på formen
>    
>    $$
>    D_k=\det
\begin{pmatrix}a_{1} & a_{3} & a_{5} & a_{7} & \cdot  & \cdot  & a_{2k-1} \\
1 & a_{2} & a_{4} & \cdot  & \cdot  & \cdot  & a_{2k-2} \\
0 & a_{1} & a_{3} & a_{5} & \cdot  & \cdot  & a_{2k-3} \\
0 & 1 & a_{2} & \cdot  & \cdot  & \cdot  & a_{2k-4} \\
0 & 0 & a_{1} & \cdot  & \cdot  & \cdot  & \cdot  \\
\cdot  & \cdot  & \cdot  & \cdot  & \cdot  & \cdot  & \cdot  \\
\cdot  & \cdot  & \cdot  & \cdot  & \cdot  & \cdot  & a_k\end{pmatrix}
>    $$
>    
>    er positive, dvs $D_k>0$.

#### Stabilitet for inhomogene systemer

> [!info] 2.47 Asymptotisk stabilitet for inhomogene systemer
> Et inhomogent system $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}+\mathbf{u}(t)$ er asymptotisk stabilt hvis og kun hvis det tilsvarende homogene system er asymptotisk stabilt.

> [!info] 2.48+2.49 BIBO-stabilitet
> Det inhomogene system $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}+\mathbf{u}(t)$ siges at være BIBO-stabilt hvis løsningerne $\mathbf{x}(t), t \in [t_{0},\infty[$ hørende til enhver begrænset påvirkning $\mathbf{u}$ er begrænsede.
> Det inhomogene system er BIBO-stabilt hvis og kun hvis det tilhørende homogene system er asymptotisk stabilt.

## Talfølger

#### Form:

$$
\{x_{1}, x_{2}, \dots, x_N\}, N \in \mathbb{N}
$$

#### Konvergens

> [!info] 4.5 Konvergens for talfølger
> En talfølge $\{x_n\}_{n=1}^\infty$ siges at være konvergent hvis der findes et tal $s \in \mathbb{C}$ således at 
> $$
> x_n \to s \text{ for } n\to \infty.
> $$
> Ellers er den divergent.

> [!info] 4.10 Regler for konvergens af to talrækker
> Hvis $x_n\to x$ og $y_n\to y$ gælder
> 1.
> $$
> \alpha x_n+\beta y_n \to \alpha x+ \beta y,\forall\alpha\beta \in \mathbb{C}
> $$
> 2.
> $$
> x_n\cdot y_n \to x\cdot y
> $$
> 3. Hvis $y\neq 0$ er $y_n\neq 0$ for et vist trin og
> $$
> \frac{x_n}{y_n} \to \frac{x}{y}
> $$
> 4. Hvis $x_n, y_n \in \mathbb{R}$ og $x_n≤y_n$ er $x≤y$

## Uendelige rækker

#### Form:

$$
a_{1}+a_{2}+a_{3}+\dots+a_n+\dots = \sum_{n=1}^{\infty} a_n \, 
$$

Den $N$'te afsnitssum $S_N$:
$$
S_N = a_{1}+a_{2}+a_{3}+\dots+a_N = \sum_{n=1}^{N} a_n \, 
$$

#### Konvergens generelt

> [!info] 4.15 Definition på konvergens for uendelige rækker
> Hvis talfølgen $S_N=\sum_{n=1}^{N}a_n  \,$ er konvergent med grænseværdien $S$ for $N\to \infty$ siges $\sum_{n=1}^{\infty} a_n \,$ at være konvergent med sum $S$, $\sum_{n=1}^{\infty} a_n \,=S$.
> 
> Hvis $S$ er divergent, er $\sum_{n=1}^{\infty} a_n \,$ divergent og tillægges ingen værdi.

> [!info] 4.17 Konvergens for to uendelige rækker
> Hvis $\sum_{n=1}^{\infty} a_n \,$ og $\sum_{n=1}^{\infty} b_n \,$ er konvergente er $\sum_{n=1}^{\infty} (\alpha a_n+\beta b_n) \,$ konvergent med sum $\alpha \sum_{n=1}^{\infty} a_n \, + \beta \sum_{n=1}^{\infty} b_n \,$.

#### Konvergenskriterier

> [!info] 4.19 $n$'te ledskriteriet
> Hvis $\sum_{n=1}^{\infty} a_n \,$ er konvergent gælder 
> $$a_n\to0 \text{ for } n\to \infty.
> $$
> Dette er ensbetydende med:
> Hvis $a_n$ ikke går mod $0$ for $n\to \infty$ er $\sum_{n=1}^{\infty} a_n \,$ divergent.

> [!info] 4.20 Sammenligningskriteriet
> For $0≤a_n≤b_n$:
> 
> 1. Hvis $\sum_{n=1}^{\infty} b_n \,$ er konvergent er $\sum_{n=1}^{\infty} a_n \,$ også konvergent.
> 2. Hvis $\sum_{n=1}^{\infty} a_n \,$ er divergent er $\sum_{n=1}^{\infty} b_n \,$ også divergent.

> [!info] 4.24 Ækvivalentskriteriet
> To rækker $\sum_{n=1}^{\infty} a_n \,$ og $\sum_{n=1}^{\infty} b_n \,$ med positive tal er ækvivalente hvis der findes en konstant $C>0$ så
> $$
> \frac{a_n}{b_n}\to C.
> $$
> I så fald er begge rækker konvergente, eller begge rækker divergente.

> [!info] 4.30 Kvotientkriteriet
> Antag $a_n\neq 0$ for alle $n$ og der findes et $C>0$ så $\mid\frac{a_{n+1}}{a_n}\mid\to C$ for $n\to \infty$.
> 
> 1. Hvis $C<1$ er $\sum_{n=1}^{\infty} a_n \,$ absolut konvergent
> 2. Hvis $C>1$ er $\sum_{n=1}^{\infty} a_n \,$ divergent
> 3. Hvis $C=1$ kræves yderligere info.

#### Absolut og betinget konvergens

> [!info] 4.26+4.27 Definition på absolut konvergens
> $\sum_{n=1}^{\infty} a_n \,$ er absolut konvergent hvis $\sum_{n=1}^{\infty} |a_n| \,$ er konvergent.
> 
> Hvis $\sum_{n=1}^{\infty} a_n \,$ er absolut konvergent er rækken konvergent.

> [!info] 4.28 Definition på betinget konvergens
> $\sum_{n=1}^{\infty} a_n \,$ er betinget konvergent hvis $\sum_{n=1}^{\infty} a_n \,$ er konvergent og $\sum_{n=1}^{\infty} |a_n| \,$ er divergent.

#### Summer

> [!info] 4.33 Integralkriteriet
> Lad $f:[1,\infty[\to[0,\infty[$ være kontinuert og aftagende.
> Betragt $\sum_{n=1}^{\infty}a_n=\sum_{n=1}^{\infty} f(n) \,  \,$
> 
> 1. Hvis $\int_{1}^{\infty} f(x) \, dx$ er konvergent er $\sum_{n=1}^{\infty} f(x) \,$ konvergent og
>    
>    $$
>    \int_{1}^{\infty} f(x) \, dx ≤\sum_{n=1}^{\infty} f(n)≤\int_{1}^{\infty}f(x)  \, dx  \, +f(1)
>    $$
> 2. Hvis $\int_{1}^{\infty} f(x) \, dx$ er divergent er $\sum_{n=1}^{\infty} f(n) \,$ divergent.

> [!info] 4.35 $(i)$ "Metode 1"
> Antag $f:[1, \infty[\to[0, \infty[$ er kontinuert og aftagende for $x≥N, n \in \mathbb{N}$.
> Antag $\int_{N}^{\infty} f(x) \, dx$ er konvergent. Da gælder
> $$
> \int_{N+1}^{\infty} f(x) \, dx≤\sum_{n=N+1}^{\infty} a_n \, ≤ \int_{N}^{\infty} f(x) \, dx.
> $$
> Vælg derfor $N \in \mathbb{N}$ således at
> $$
> \int_{N}^{\infty} f(x) \, dx ≤ \epsilon
> $$

> [!info] 4.35 $(ii)$ "Metode 2", mere præcis
> Antag $f:[1, \infty[\to[0, \infty[$ er kontinuert og aftagende for $x≥N, n \in \mathbb{N}$.
> Antag $\int_{N}^{\infty} f(x) \, dx$ er konvergent. Da gælder
> $$
> \int_{N+1}^{\infty} f(x) \, dx ≤\sum_{n=N+1}^{\infty} f(n)≤\int_{N+1}^{\infty} f(x) \, dx +f(N+1) \, 
> $$
> Vælg derfor $N \in \mathbb{N}$ således at
> $$
> \int_{N+1}^{\infty} f(x) \, dx+f(N+1)≤\epsilon
> $$

> [!info] 4.38 Leibniz' kriterium
> Antag $b_i>0, b_{i}≥b_{i+1}, \forall i\in\mathbb{N}$ (positive og aftagende) og $b_n\to 0$ for $n\to \infty$.
> Da er $b_{1}-b_{2}+b_{3}-b_{4}+\dots=\sum_{n=1}^{\infty} (-1)^{n-1}b_n \,$ konvergent og
> $$
> \mid \sum_{n=1}^{\infty} (-1)^{n-1}b_n - \sum_{n=1}^{N} (-1)^{n-1}b_n \mid ≤b_{N+1} \,  \, .
> $$

## Uendelige rækker med variable led

#### Form:

Kvotientrække:
$$
f(x)=\sum_{n=0}^{\infty} x^n \, = 1+x+x^2+\dots
$$
Potensrække:
$$
f(x)=\sum_{n=0}^{\infty}c_nx^n = c_0 + c_{1}x+c_{2}x^2+\dots\, 
$$

#### Konvergens og summer

> [!info] 5.2 Konvergens og sum for kvotientrække
> En kvotientrække $\sum_{n=0}^{\infty}x^n  \,$ er konvergent hvis og kun hvis $|x|<1$.
> For $|x|<1$ er summen
> $$
> \frac{1}{1-x}
> $$
> For rækken $\sum_{n=N}^{\infty} x^n \,,N \in \mathbb{N},|x|<1$ er summen
> $$
> \frac{x^N}{1-x}
> $$

> [!info] 5.13 Konvergensscenarier for potensrække
> For en potensrække $\sum_{n=0}^{\infty} c_nx^n \,$ gælder ét af følgende:
> 
> 1. Rækken er kun konvergent for $x=0$
> 2. Rækken er absolut konvergent for alle $x \in \mathbb{R}$
> 3. Der findes et tal $\rho>0$ således at rækken er absolut konvergent for $|x|<\rho$ og divergent for $|x|>\rho$.

##### Funktioner som uendelige rækker

> [!info] 5.7 Funktionsfremstilling som uendelig række
> Antag at $f:I\to \mathbb{C}$ er vilkårligt ofte differentiabel, og at der findes en konstant $C>0$ således at $|f^{(n)}(x)|≤C, \forall x\in I,\forall n\in\mathbb{N}$.
> Lad $x_0\in I$. Så gælder at
> $$
> f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(x_0)}{n!}(x-x_0)^n, \forall x\in I. \, 
> $$

> [!info] 5.17 Differention af potensrække
> Givet en potensrække $\sum_{n=0}^{\infty} c_nx^n \,$, med konvergensradius $\rho>0$ definer
> $$
> f(x):=\sum_{n=0}^{\infty} c_nx^n  \,,x\in]-\rho,\rho[. 
> $$
> Så er funktionen $f$ differentiabel, og
> $$
> f'(x)=\sum_{n=1}^{\infty}nc_nx^{n-1}  \,. 
> $$
> Generelt
> $$
> f^{(k)}(x)=\sum_{n=k}^{\infty} n\cdot (n-1)\cdot \dots\cdot (n-k+1)c_nx^{n-k}. \, 
> $$

#### Uniform konvergens

> [!info] 5.28 Definition af uniform konvergens
> Antag at $\sum_{n=1}^{\infty} f_n(x) \,$ er konvergent for $x\in I$, og sæt 
> $$
> f(x):=\sum_{n=1}^{\infty} f_n(x), x\in I. \, 
> $$
> Den uendelige række $\sum_{n=1}^{\infty} f_n(x) \,$ er uniform konvergent hvis der for ethvert $\epsilon>0$ findes et $N_0\in\mathbb{N}$ således at 
> $$
> \mid f(x)-\sum_{n=1}^{N} f_n(x)\mid≤\epsilon, \forall N≥N_0
> $$

> [!info] 5.31 Definition af majorantrække
> Lad funktionerne $f_{1},f_{2},\dots,f_n,\dots$ være definerede på et interval $I$ og betragt den formelle række
> $$
> \sum_{n=1}^{\infty} f_n(x),x\in I \, 
> $$
> 
> 1. En række $\sum_{n=1}^{\infty} k_n \,$ med konstante og positive led $k_n$ er en majorantrække for rækken ovenfor på intervallet $I$, hvis der for et hvert $n\in \mathbb{N}$ gælder at
>    
>    $$
>    \mid f_n(x)|≤k_n, \forall x\in I.
>    $$
> 2. En række $\sum_{n=1}^{\infty} k_n \,$ der er konvergent og opfylder ovenstående ulighed siges at være en konvergent majorantrække for $\sum_{n=1}^{\infty} f_n(x),x\in I$.

> [!info] 5.33 Uniform konvergens pba. majorantrække
> Antag at funktionerne $f_{1},f_{2},\dots,f_n,\dots$ er definerede på et interval $I$ og at rækken $\sum_{n=1}^{\infty} f_n(x) \,, x\in I$ har en konvergent majorantrække.
> Så konvergerer den uendelige række $\sum_{n=1}^{\infty} f_n(x) \,$ uniformt på intervallet $I$.

>[!info] 5.35 Kontinuitet af sumfunktion
>Hvis
>1. Funktionerne $f_{1}, f_{2}, \dots, f_n, \dots$ er definerede og kontinuerte på et interval $I$.
>2. Rækken $\sum_{n=1}^{\infty} f_n(x) \,$ har en konvergent majorantrække på $I$ (eller, mere generelt, rækken konvergerer uniformt).
>
>Så er sumfunktionen
>$$
>f(x)=\sum_{n=1}^{\infty} f_n(x) \, , x\in I
>$$
>kontinuert.

>[!info] 5.38 Integration af potensrække
>For en potensrække $\sum_{n=0}^{\infty} c_nx^n \,$ med konvergensradius $\rho>0$ gælder for $b\in]-\rho, \rho[$ at
>$$
>\int_{0}^{b} \sum_{n=0}^{\infty} c_nx^n \,  \, dx =\sum_{n=0}^{\infty} \frac{c_n}{n+1}b^{n+1} \, .
>$$
## Fourierrækker

#### Definitioner

> [!info] 6.1 Fourierrækken
> Til en $2\pi$-periode funktion $f$ knyttes en uendelig række, Fourierrækken:
> $$
> f\sim \frac{1}{2}a_0+\sum_{n=1}^{\infty} a_n\cos nx+b_n\sin nx, \, 
> $$
> hvor
> $$
> a_n = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\cos nx \, dx 
> $$
> $$
> b_n = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\sin nx \, dx 
> $$
> $$
> a_{0}=\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x) \, dx 
> $$

> [!info] 6.5 Forskydning
> Hvis $g(x)$ er en $2\pi$-periodisk funktion er
> $$
> \int_{-\pi}^{\pi} g(x) \, dx = \int_{a-\pi}^{a+\pi} g(x) \, dx \forall a\in\mathbb{R}
> $$

> [!info] 6.6 Lige og ulige funktioner
> **Lige**
> $f(x)$ er lige hvis $\int_{-a}^{a} f(x) \, dx=2\int_{0}^{a} f(x) \, dx, \forall a>0$. Da er $b_n=0$ og
> $$
> a_n=\frac{2}{\pi}\int_{0}^{\pi} f(x)\cos nx \, dx .
> $$
> 
> $f(x)$ er ulige hvis $\int_{-a}^{a} f(x) \, dx=0,\forall a>0$. Da er $a_n=0$ og 
> $$
> b_n=\frac{2}{\pi}\int_{0}^{\pi} f(x)\sin nx \, dx. 
> $$

> [!info] 6.25 Fourierrækken på kompleks form
> Ved Fourrierrækken for $f$ på kompleks form forstås
> $$
> f\sim \sum_{n=-\infty}^{\infty} c_ne^{inx}, \, 
> $$
> hvor
> $$
>    c_n = \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)e^{-inx} \, dx.
> $$
> Vi har yderligere for $n\in\mathbb{N}$ at (6.26)
> $$
> c_0=\frac{1}{2}a_0
> $$
> $$
> c_n=\frac{1}{2}(a_n-ib_n),\text{ } c_{-n}=\frac{1}{2}(a_n+ib_n) \underbrace{ \implies }_{ f\in\mathbb{R} } c_{n}=\overline{c_{-n}}.
> $$
> $$
> a_{0}=2c_{0}, \text{ } a_n=c_n+c_{-n}, \text{ } b_n=i(c_n-c_{-n})
> $$

#### Kontinuitet og differentiabilitet

> [!info] Definition på stykkevis kontinuitet
> Lad
> $$
> f(x^+) = \lim_{ y \to x^+ } f(y), f(x^-)=\lim_{ y \to x^- } f(y).
> $$
> Hvis $f$ er kontinuert i $x$ er $f(x^+)=f(x^-)=f(x)$.
> 
> **Stykkevis kontinuitet:**
> $f$ ($2\pi$-periodisk) er stykkevis kontinuert hvis $f(x^+)$ og $f(x^-)$ findes for alle $x$ og $f(x^+)=f(x^-)$ for alle $x$ pånær et endeligt antal $-\pi≤x_{1}<x_{2}<\dots<x_p≤\pi, p \in \mathbb{N}$.

> [!info] 6.13 Definition på stykkevis differentiabilitet
> $f$ ($2\pi$-periodisk) er stykkevis differentiabel hvis den er stykkevis kontinuert og der for ethvert $x$ findes to tal $\alpha,\beta$ så
> $$
> \frac{f(x+\Delta x)-f(x)}{\Delta x}\to\alpha \text{ for } \Delta x\to0^+ \text{ og}
> $$
> $$
> \frac{f(x+\Delta x)-f(x)}{\Delta x}\to \beta \text{ for } \Delta x \to 0^-.
> $$

#### Fouriers sætning

> [!info] 6.16 Fouriers sætning
> 
> 1. Hvis $f$ er en $2\pi$-periodisk stykkevis differentiabel funktion konvergerer Fourierrækken for alle $x$.
> 
> 2. Hvis $f$ er kontinuert i $x$ gælder 
>    
>    $$
>    f(x)=\frac{1}{2}a_{0}+\sum_{n=1}^{\infty} (a_n\cos nx+b_n\sin nx). \, 
>    $$
> 
> 3. Hvis $f$ er diskontinuert i $x$ gælder
>    
>    $$
>    \frac{1}{2}a_{0} + \sum_{n=1}^{\infty} (a_n\cos nx+b_n\sin nx)=\underbrace{ \frac{f(x^+)+f(x^-)}{2} }_{ \text{middelværdi} } \, .
>    $$

>[!info] 6.17 Uniform konvergens for Fourierrækker
>Antag at $f$ er en kontinuert, stykkevis differentiabel og $2\pi$-periodisk funktion. Så gælder flg:
>1. For ethvert $x\in\mathbb{R}$ er
>$$
>f(x)=\frac{1}{2}a_{0}+\sum_{n=1}^{\infty} (a_n\cdot \cos nx + b_n\cdot \sin nx). \, 
>$$
>2. Fourierrækken konvergerer uniformt mod $f$ og den maksimale afvigelse mellem $f(x)$ og afsnitssummen $S_N(x)$ kan vurderes ved
>$$
>\mid f(x)-S_N(x)\mid≤\frac{1}{\sqrt{ N }} \frac{1}{\sqrt{ \pi }} \sqrt{ \int_{-\pi}^{\pi} \mid f'(t)\mid^2 \, dt  }.
>$$
#### Approximation via fourierrækken

> [!info] 6.12 Konvergens for Fourierrækken
> Hvis $f$ er stykkevis differentiabel, $2\pi$-periodisk og kontinuert, så konvergerer fourierrækken mod $f(x), \forall x\in\mathbb{R}$.

> [!info] 6.21 Approximation via Fourierrækken
> Antag at funktionen $f$ er $2\pi$-periodisk, kontinuert og stykkevis differentiabel, med Fourierkoefficienter $a_n, b_n$. Så gælder for ethvert $N\in\mathbb{N}$ at
> $$
> \mid f(x)-S_N(x)\mid \sum_{n=N+1}^{\infty} (|a_n|+|b_n|), \forall x\in\mathbb{R}. \, 
> $$
> Vælg derfor $N$ således at
> $$
> \sum_{n=N+1}^{\infty} (|a_n|+|b_n|)≤\epsilon \, 
> $$

## Fourierrækkemetoden

#### System:

Vi betragter differentialligningssystemet $(*)$:
$$
\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}+\mathbf{b}u, y=\mathbf{d}^\top\mathbf{x},
$$
med overføringsfunktionen
$$
H(s)=-\mathbf{d}^\top(\mathbf{A}-s\mathbf{I})^{-1}\mathbf{b},
$$
hvor $\det(\mathbf{A}-s\mathbf{I})\neq 0$. Hvis $u(t)=e^{st}$ er $y(t)=H(s)e^{st}$ en partikulær løsning til $(*)$, (stationær løsning).

Lad ydermere $(*)$ være asymptotisk stabilt, dvs. for alle løsninger $\mathbf{x}(t)$ til $\dot{\mathbf{x}}=\mathbf{A}\mathbf{x}$ gælder $\mathbf{x}(t)\to0$ for $t\to \infty$ (ensbetydende med at alle egenværdier for $\mathbf{A}$ har negativ realdel).

#### Fourierrækkemetoden

> [!info] 7.7 Stationær løsning
> Betragt systemet $(*)$.
> For enhver påvirkning på formen
> $$
> S_N(t)=\sum_{n=-N}^{N} c_ne^{int} \, 
> $$
> fås løsningen
> $$
> y_N(t)=\sum_{n=-N}^{N} c_nH(in)e^{int} \, .
> $$

> [!info] 7.8 Fourierrækkemetoden
> Betragt systemet $(*)$.
> Hvis $u(t)$ er $2\pi$-periodisk, stykkevis differentiabel og kontinuert med $u(t)=\sum_{n=-\infty}^{\infty} c_ne^{int} \,$ er det stationære svar
> $$
> y(t)=\sum_{n=-\infty}^{\infty} c_nH(in)e^{int}. \, 
> $$

#### Parsevals sætning

> [!info] 6.30 Parsevals sætning
> Hvis $f\in L^2(-\pi,\pi)$ og 
> $$
> f\sim \frac{1}{2}a_{0} + \sum_{n=1}^{\infty} (a_n\cos nx + b_n\sin nx)  \, = \sum_{n=-\infty}^{\infty} c_ne^{inx} \,  
> $$
> gælder
> $$
> P(f)=\frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x)|^2 \, dx =\frac{1}{4}a_{0}^2+\frac{1}{2}\sum_{n=1}^{\infty} (|a_n|^2+|b_n|^2) = \sum_{n=-\infty}^{\infty} |c_n|^2.
> $$

> [!info] Metode: Relativ tolerence
> Givet en relativ tolerence $\epsilon_R$, $0<\epsilon_R<1$ bestem $N$, så
> $$
> \frac{P(S_N)}{P(f)}≥1-\epsilon_R.
> $$

## Potensrækkemetoden

> [!info] 5.21 Identitetssætningen for potensrækker
> Hvis koefficienterne $c_n$ for et passende $\rho>0$ opfylder at
> $$
> \sum_{n=0}^{\infty} c_nx^n=0, x \in ]-\rho, \rho[ \, 
> $$
> så er $c_n=0$ for alle $n$.

## Fouriertransformation
>[!info] 6.40 Regneregler for Fouriertransformationen
>For $f\in L^1(\mathbb{R})$ gælder flg. regneregler
>
>1. Hvis $f$ er en lige funktion så er
>$$
>\hat{f}(\gamma)=2\int_{0}^{\infty} f(t)\cos(2\pi t\gamma) \, dt. 
>$$
>2. Hvis $f$ er en ulige funktion, så er
>$$
>\hat{f}(\gamma)=2i\int_{0}^{\infty} f(t)\sin(2\pi t\gamma) \, dt. 
>$$
>3. Lad $a\in\mathbb{R}$. Fouriertransformationen af funktionen $g(t)=f(t-a)$ er givet ved
>$$
>(\mathcal{F}g)(\gamma)=\hat{f}(\gamma)e^{-2\pi ia\gamma}.
>$$
>4. Lad $\theta \in\mathbb{R}$. Fouriertransformationen af funktion $h(t)=f(t)e^{2\pi i\theta t}$ er givet ved
>$$
>(\mathcal{F}h)(\gamma)=\hat{f}(\gamma-\theta).
>$$
>5. Hvis $f$ er differentiabel og $f'\in L^1(\mathbb{R})$, så er
>$$
>(\mathcal{F}f')(\gamma)=2\pi i\gamma \hat(f)(\gamma).
>$$
>



