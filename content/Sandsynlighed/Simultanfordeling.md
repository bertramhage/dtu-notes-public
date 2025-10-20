# Simultanfordeling

> Uge 8 27/10/23
> 
> Chap. 5.1 + 5.2

### Ligefordeling i 2 variable

**Sandsynligheder som andele af areal**

Antag at et punkt med sikkerhed falder i området $D$ med areal $A(D)$.

Sandsynligheden for, at et punkt $(X,Y)$ falder i området $C$, hvor $C\subset D$, er lig den andel som $A(C)$ udgør af det totale areal: $P((X,Y)\in C)=\frac{A(C)}{A(D)}$.

---

Hvis $X$ og $Y$ begge er uniformt fordelit på et interval og uafhængige, da er $(X,Y)$ uniformt fordelt på et rektangel.

---

###### Eksempel

Antag at $X$ og $Y$ er uafhænigige ligefordelte på enhedsintervallet $(0,1)$.

Spm: Find

$$
P\left(Y\ge\frac{1}{2}|Y\ge1-2X\right)
$$

Svar: Først benytter vi $P(A|B)=\frac{P(A\cap B}{P(B)}$

$$
P\left(Y\ge\frac{1}{2}|Y\ge1-2X\right)=\frac{P(Y\ge\frac{1}{2}, y\ge1-2X)}{P(Y\ge1-2X)}
$$

Nævneren:

$$
P(Y\ge1-2X) = 1-P(Y<1-2X)=1-\frac{1}{4}=\frac{1}{3}
$$

Tælleren:

$$
P\left(Y\ge\frac{1}{2}, Y\ge1-2X\right) = \frac{1}{2}\frac{1}{2}\frac{1}{4}+\frac{1}{2}\frac{3}{4}\frac{7}{16}
$$

Altså er 

$$
P\left(Y\ge\frac{1}{2}|Y\ge1-2X\right) = \frac{\frac{7}{16}}{\frac{3}{4}}=\frac{7}{12}
$$

### Simultan (joint) fordeling for 2 kontinuerte variable

Der gælder at

$$
f(x,y)\ge 0, \int_{-\infty}^\infty\int_{-\infty}^\infty f(x,y)dxdy=1
$$

$$
P((X,Y)\in B) = \int_B f(x,y)dxdy
$$

##### Marginale fordelinger

$$
f_X(x)=\int_{-\infty}^\infty f(x,y)dy, f_y(y)=\int_{-\infty}^\infty f(x,y)dx
$$

###### Eksempel

Et punkt vælges i enhedskvadratet i henhold til den simultane tæthed $f(x,y)=c(x^2+4xy), 0<x<1, 0<y<1$ for en konstant $c$.

Spm: Bestem $c$

Svar:

$$
1=\int\int f(x,y)dxdy = \int_0^1\int_0^1 c(x^2+4xy)dxdy\\
=\int_0^1 c(x^2+2xdx)=\frac{4c}{3}\implies c=\frac{3}{4}
$$

Spm: Find $P(X≤a), 0<a<1$

Svar:

$$
\int_0^a\int_0^1 \frac{3}{4}(x^2+4xy)dxdy=\int_0^a \frac{3}{4}(x^2+2x)dx=\frac{3}{4}\left(\frac{a^3}{3}+a^2\right)
$$

dette er fordelingfunktionen for $X$ evalueret i $a$.

Spm: Find $P(Y≤b), 0<Y<1$

Svar:

$$
\int_0^b\int_0^1 \frac{3}{4}(x^2+4xy)dxdy=\int_0^b \frac{3}{4}(\frac{1}{3}+2y)dy=\frac{3}{4}\left(\frac{b}{3}+b^2\right)
$$

dette er fordelingsfunktionen for $Y$ evalueret i $b$.

##### Uafhængighed

Den stokastiske variable $X$ og $Y$ med tæthed $f(x,y)$ marginale tætheder $f_X(x)$ og $f_Y(y)$ er uafhængige hvis og kun hvis

$$
f(x,y) = f_X(x)\cdot f_Y(y), \forall (x,y).
$$

### Fordeling af maksimum og minimum

Der gælder for n identisk fordelte stokastiske variable $X_i$ med fordelingsfunktion $F(x)$, hvor $X_{min}=X_{(1)}≤X_{(2)}≤...≤X_{(n)}=X_{max}$.

$$
\begin{gathered}
\mathrm{P}\left(X_{(n)} \leq x\right)=\mathrm{P}\left(X_1 \leq x\right) \mathrm{P}\left(X_2 \leq x\right) \cdots \mathrm{P}\left(X_n \leq x\right)=F(x)^n \\
\mathrm{P}\left(X_{(1)} \leq x\right)=1-\mathrm{P}\left(X_1>x\right) \mathrm{P}\left(X_2>x\right) \cdots \mathrm{P}\left(X_n>x\right) \\
=1-(1-F(x))^n
\end{gathered}
$$

Lad $U$ og $V$ være to uafhængige ligefordelte $(0,1)$ variable. Lad $X$ være den mindste af $U$ og $V$.

- Repræsenter hændelsen $(X≥x) (0<x<1)$ som et område i planen og find $P(X≥x)$ som arealet af dette område.

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_HmGAAl/Skærmbillede%202023-11-02%20kl.%2015.49.55.png" alt="Skærmbillede 2023-11-02 kl. 15.49.55.png" width="234" data-align="center">

$$
P(X≥x) = (1-x)^2
$$

Eller

$$
F(x)=P(X≤x)=1-(1-x)^2\\
(F_{min}(x)=P(X_{(1)}≤x)=1-(1-F(x))^n)
$$

- Find fordelingsfunktionen og tætheden af $X$ og skitser grafen af disse funktioner

$$
P(X≤x)=F_X(x)=1-P(X≥x)=1-(1-x)^2
$$

Tætheden:

$$
f_X(x)=\frac{dF_X(x)}{dx}=2(1-x).
$$

### Fordeling af ordnede variable

Lad $X_i$, være i.i.d. $(i=1, \ldots, n)$ med fordelingsfunktion $F(x)$ og tæthed $f(x)$.

Lad $X_{(k)}$ igen benævne den $k$ 'te mindste, så

$$
X_{(1)} \leq X_{(2)} \leq \cdots\leq X_{(n-1)} \leq X_{(n)} \text {. }

$$

$X_{(k)}$ har tæthed $f_k(x)$ givet ved

$$
f_k(x)=n\left(\begin{array}{c}
n-1 \\
k-1
\end{array}\right) f(x) F(x)^{k-1}(1-F(x))^{n-k}
$$

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

###### Der gælder altså at

$$
f_R(r)=re^{-\frac{1}{2}r^2},\\
P(R≤r)=F_R(r)=1-e^{-\frac{1}{2}r^2}
$$
