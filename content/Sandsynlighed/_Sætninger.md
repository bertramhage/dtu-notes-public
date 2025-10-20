## Kapitel 1: Intro

>[!info] Naiv sandsynlighed
>$$
>P_{naiv}(A)=\frac{\#successer}{\#mulige udfald}
>$$

>[!info] Uafhængighed
>$A$ og $B$ er uafhængige hændelser. Da gælder
>$$
>P(AB)=P(A)P(B)\Leftrightarrow P(A|B)=P(A)\Leftrightarrow P(B|A)=P(B)
>$$

#### Betinget sandsynlighed
>[!info] Betinget sandsynlighed
>For to begivenheder $A$ og $B$ er
>$$
>P(A|B)=\frac{P(A\cap B)}{P(B)}\Leftrightarrow P(A\cap B)=P(A|B)P(B)
>$$

>[!info] Total sandsynlighed
>For to begivenheder $A$ og $B$ er
>$$
>P(A)=P(A|B)P(B)+P(A|B^c)P(B^c)
>$$

>[!info] Bayes' regel
>For to begivenheder $A$ og $B$ er
>$$
>\begin{align}
>P(A|B)&=\frac{P(B|A)P(A)}{P(B)}&\Leftrightarrow  \\
>P(A|B)&=\frac{P(B|A)P(A)}{P(A)P(B|A)+P(A^c)P(B|A^c)}
\end{align}
>$$

>[!info] Inklusion/ekslusion
>For to begivenheder $A$ og $B$ er
>$$
>P(A\cup B)=P(A)+P(B)-P(A\cap B)
>$$
>$\implies$
>For $A=A_1\cup A_{2}\cup\dots \cup A_n$ er
>$$
>\begin{align}
>P(A) =& P(A_{1})+P(A_{2})+\dots+P(A_n) \\
>&-P(A_{1}\cap A_{2})-P(A_{1}\cap A_{3})-\dots-P(A_{n-1}\cap A_n)
>\end{align}
>$$

## Kapitel 2: Gentagne forsøg
|                   | Order Matters      | Order Doesn't Matter |
|-------------------|--------------------|----------------------|
| With Replacement  | $n^k$                | $\begin{pmatrix}n+k-1\\k\end{pmatrix}$          |
| Without replacement| $\frac{n!}{(n-k)!}$|$\begin{pmatrix}n\\k\end{pmatrix}$|

>[!info] Binomial fordeling
>For $k$ succeser i $n$ forsøg
>$$
>P(k)=\begin{pmatrix}n\\ k \end{pmatrix}p^k (1-p)^{n-k}
>$$
>hvor
>$$
>\begin{pmatrix}n\\ k \end{pmatrix} = \frac{n!}{k!(n-k)!}
>$$

>[!info] Normalapproximation til binomialfordeling
>Lad $\mu=np$ være middelværdien og $\sigma=\sqrt{ npq }$ være sd. Da er 
>$$
>P(a \text{ til } b) \approx \Phi\left( \frac{b+\frac{1}{2}-\mu}{\sigma} \right)-\Phi\left( \frac{a-\frac{1}{2}-\mu}{\sigma} \right)
>$$ 

>[!info] Hypergeometrisk fordeling
>For $g$ succeser i en stikprøve på $n$, uden tilbagelægning. 
>Lad $G$ være totale antal succeser i populationen og$N$ være populationsstørelsen.
>Da er
>$$
>P(g\text{ succeser})=\frac{\begin{pmatrix}G\\g\end{pmatrix}\begin{pmatrix}N-G\\ n-g\end{pmatrix}}{\begin{pmatrix}N\\n\end{pmatrix}}.
>$$
## Kapitel 3: Stokastiske variable
>[!info] Forventet værdi af stokastisk variabel
>Lad $X$ være en stokastisk variabel. Da er
>$$
>E(X)=\sum_x xP(X=x)
>$$

>[!info] Definition af varians
>For en stokastisk variabel $X$ gælder
>$$
>Var(X) = E[(X-E(X))^2]=\sum_x(x-E(X))^2P(X=x)
>$$
>Variansen kan beregnes
>$$
>Var(X)=E(X^2)-(E(X))^2
>$$

>[!info] Forventet værdi for linearkombination
>Lad $X$ være en stokastisk variabel og $a$ og $b$ konstanter. Da er
>$$
>E(aX+b)=aE(X)+b
>$$

>[!info] Varians for linearkombination
>Lad $X$ være en stokastisk variabel og $a$ og $b$ konstanter. Da er
>$$
>Var(aX+b)=a^2Var(X) \implies
>$$
>$$
>SD(aX+b)=|a|SD(X)
>$$

>[!info] Middelværdi og varians for sum af lineært uaf. stokastiske variable
>Lad $X$ og $Y$ være lineært uafhængige stokastiske variable, og lad $Z=X+Y$.
>Da er 
>$$
>\text{middel}(Z) = \text{middel}(X)+\text{middel}(Y),
>$$
>$$
>\text{SD}(Z) = \text{SD}(X)+\text{SD}(Y)
>$$

>[!info] Markovs ulighed (kender ikke sd)
>Øvre grænse for afvigelse givet grænse $a$
>$$
>P(X≥a)≤ \frac{E(X)}{a}.
>$$

>[!info] Chebychevs ulighed (kendt sd)
>Øvre grænse for afvigelse med $k$ standardafvigelser
>$$
>P(|X-E(X)|≥kSD(X))≤ \frac{1}{k^2}
>$$

#### Summer
>[!info] Forventet værdi for summer
>Lad $X_i, i\in{1,2,..,n}$ være stokastiske variable og $S_n=X_{1}+\dots+X_n$. Da er
>$$
>E(S_n)=E(X_{1})+\dots+E(X_n).
>$$
>Hvis alle $X_i$ har samme fordeling er
>$$
>E(S_n)=nE(X_{1})
>$$

>[!info] Varians og SD for summer
>Lad $X_i, i\in{1,2,..,n}$ være stokastiske **uafhængige** variable og $S_n=X_{1}+\dots+X_n$. Da er
>$$
>Var(S_n) = Var(X_{1})+\dots+Var(X_n).
>$$
>Hvis alle $X_i$ har samme fordeling er
>$$
>Var(S_n)=nVar(X_{1})
>$$
>
>**Kvadratrodsloven**
>Hvis alle $X_i$ har samme fordeling og $\bar{X}_n=\frac{S_n}{n}$ er
>$$
>SD(S_n)=SD(X_{1})\sqrt{ n } \text{,  } SD(\bar{X}_n)=\frac{SD(X_{1})}{\sqrt{ n }}
>$$

## Kapitel 4: Kontinuerte fordelinger
>[!info] Integralformel
>$$
>P(a≤X≤b)=\int_{a}^{b} f(x) \, dx 
>$$
>

>[!info] Median af en fordeling
>Lad $X$ være en stokastisk variabel med en given fordeling og fordelingsfunktion $F(x)$. 
>Da er medianen $m$ givet ved
>$$
>P(X≤m)=F(X)=\frac{1}{2}
>$$

>[!info] Forventningsværdi af funktion af stokastisk variabel
>Lad $X$ være en stokastisk variabel med tæthedsfunktion $f$. Da er
>$$
>E(g(x))=\int_{-\infty}^{\infty} g(x)f(x) \, dx \implies
>$$
>For $X\sim N(0,1)$ er
>$$
>E(|X|)=\int_{-\infty}^{\infty} |x| \frac{1}{\sqrt{ 2\pi }}e^{\frac{x^2}{2}} \, dx .
>$$

#### Overlevelsesfunktionen og Hazard rate
>[!info] Overlevelsesfunktionen definition
>For en stokastisk variabel $T$ med fordeling $F(T)$ er overlevelsesfunktionen
>$$
>G(T)=P(T>t)=1-P(T≤1)=1-F(T)
>$$

>[!info] Hazard rate definition
>Givet en stokastisk variabel $T$, med tæhedsfunktion $f(t)$ og overlevelsesfunktion $G(t)$. Hazard rate er sandsynligheden for at hændelsen indtræffer kort efter $t$, givet at den ikke er indtruffet før.
>$$
>\lambda(t)=\frac{f(t)}{G(t)}.
>$$

### Variabelskift
>[!info] En-til-en skift af variabel for tætheder
>Lad $X$ være en stokastisk variabel med tæthed $f_{X}(x)$ over et interval $[a,b]$.
>Lad $Y=g(X)$, hvor $g$ er enten konstant voksende eller konstant aftagende.
>Da er $Y$ defineret på $[g(a), g(b)]$ og tætheden for $Y$ er
>$$
>f_Y(y)=\frac{f_X(x)}{\mid \frac{dy}{dx}\mid}, y=g(x).
>$$

>[!info] Lineær variabelskift for tætheder
>Lad $X$ være en stokastisk variabel med tæthed $f_{X}(x)$. Da er
>$$
>f_{aX+b}(y)=\frac{1}{|a|}f_X\left( \frac{y-b}{a} \right).
>$$

#### Order statistics
>[!info] Order statistics
>Hvis $X_{1}, \dots ,X_n$ er uafhængige og har tæthed $f$ og fordeling $F$ er den $k$'ende order statistic, dsv. den $k$'ende mindste værdi blandt $X_{1}, \dots,X_n$ tætheden
>$$
>f_{X_{(k)}}(x)=nf(x)\begin{pmatrix}n-1 \\ k-1\end{pmatrix}(F(x))^{k-1}(1-F(x))^{n-k}
>$$
## Kapitel 5: Simultanfordelinger
>[!info] Simultan fordelingsfunktion
>Den simultane fordeling er givet
>$$
>F_{XY}(x,y) = P(X≤x, Y≤y).
>$$
>Vi bestemmer da den simultane fordeling ved
>$$
>\begin{align}
>F_{XY}(x,y)&=P(X≤x)-P(X≤x, Y>y) \\
>&=P(Y≤y)-P(Y≤y, X>x).
\end{align}
>$$

>[!info] Marginalfordeling
>$$
>f_X(x)=\int_{-\infty}^\infty f(x,y)dy, f_y(y)=\int_{-\infty}^\infty f(x,y)dx
>$$

>[!info] Marginalfordeling for diskrete variable
>$$
>P(Y=y)=\sum_{\text{all }x}P(X=x, Y=y)
>$$

>[!info] Forventningsværdi af funktion af simultanfordelte variable
>Lad $(X,Y)$ være et par stokastiske variable med den simultane tæthedsfunktion $f(x,y)$. Da er
>$$
>E(g(X,Y))=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} g(x,y)f(x,y) \, dxdy.
>$$

>[!info] Tæthed for $X+Y$
>Hvis $(X,Y)$ har tæthed $f(x,y)$ i planen er
>$$
>f_{X+Y}(z)=\int_{-\infty}^{\infty} f(x,z-x) \, dx .
>$$
>Hvis $X$ og $Y$ er uafhængige er
>$$
>f_{X+Y}(z)=\int_{-\infty}^{\infty} f_X(x)f_Y(z-x) \, dx 
>$$

>[!info] Rayleigh fordelingen
>Hvis $X$ og $Y$ er uafhængige standard normalfordelte variable har $R=\sqrt{ X^2+Y^2 }$ Rayleigh distributionen, med tætheden
>$$
>f_R(r)=re^{-\frac{1}{2}r^2}, r>0,
>$$ 
>og fordelingsfunktionen
>$$
>F_R(r)=1-e^{-\frac{1}{2}r^2}, r>0.
>$$
>Variablen $R$ repræsenterer afstanden fra centrum til et stokastisk punkt $(X,Y)$.

>[!info] Forhold mellem uafhængige normalfordelte variable
>Lad $X$ og $Y$ være uafhængige normalfordelte variable og
>$Z=\frac{X}{Y}$.
>Da er
>$$
>f_Z(z)=\int_{-\infty}^{\infty} |x|f_{X,Y}(x,xz) \, dx =\int_{-\infty}^{\infty} |x|f_X(x)f_{Y}(xz) \, dx 
>$$

#### Order statistics
>[!info] Tæthed og fordelinger
>For $n$ stokastiske variable $X_i$, hvor 
>$$X_{min}=X_{(1)}≤X_{(2)}≤...≤X_{(n)}=X_{max}$$
>er
>$$
>F_{X_{(i)}}(x)=P(X_{(i)}≤x)=\sum_{k=i}^{n} \begin{pmatrix}n \\ k\end{pmatrix} F(x)^k(1-F(x))^{n-k} \, 
>$$
>og
>$$
>f_{X_{(i)}}(x)=n \begin{pmatrix}n-1 \\ i-1\end{pmatrix} F(x)^{i-1}(1-F(x))^{n-i}f(x).
>$$

>[!info] For identisk fordelte variable
>For $n$ identisk fordelte stokastiske variable $X_i$ med fordelingsfunktion $F(x)$, hvor 
>$$X_{min}=X_{(1)}≤X_{(2)}≤...≤X_{(n)}=X_{max}$$
>er
>$$
>\mathrm{P}\left(X_{(n)} \leq x\right)=\mathrm{P}\left(X_{(1)} \leq x\right) \mathrm{P}\left(X_{(2)} \leq x\right) \cdots \mathrm{P}\left(X_{(n)} \leq x\right)=F(x)^n
>$$
>og
>$$
>\begin{align}
>\mathrm{P}\left(X_{(1)} \leq x\right)&=1-\mathrm{P}\left(X_1>x\right) \mathrm{P}\left(X_2>x\right) \cdots \mathrm{P}\left(X_n>x\right) \\
>&=1-(1-F(x))^n
\end{align}
>$$
## Kapitel 6: Afhængighed

#### Tætheder
>[!info] Gennemsnitlig afhængig sandsynlighed
>**For kontinuert**
>$$
>P(B)=\int P(B|X=x)f_X(x) \, dx 
>$$
>$$
>f_Y(y)=\int f_Y(y|X=x)f_X(x) \, dx 
>$$
>
>**For diskret**
>$$
>P(B)=\sum_{\text{all } x}P(B|X=x)P(X=x)
>$$
>$$
>P(Y=y)=\sum_{\text{all } x}P(Y=y|X=x)P(X=x)
>$$
>
>**Særligt tilfælde: blandet**
>$$
>f_X(x)=\sum_{\text{all } x}f_X(x|N=n)P(N=n)
>$$

>[!info] Forventningsværdi
>For stokastiske variable $X$ og $Y$ er
>$$
>E(X)=E(E(X|Y)).
>$$

>[!info] Gennemsnitlig afhængige forventning
>For stokastiske variable $X$ og $Y$ er
>$$
>E(Y) = \int_{-\infty}^{\infty} E(Y|X=x)f_Y(y) \, dy 
>$$

>[!info] Uafhænighed og co-varians
>For to variable $X$ og $Y$ er 
>$$
>X,Y \text{uaf. }\implies Cov(X,Y)=0
>$$

>[!info] Co-varians definition
>$$
>Cov(X,Y) = E[(X-\mu_X)(Y-\mu_Y)] = E(XY)-E(X)E(Y)
>$$

>[!info] Correlation definition
>$$
>Corr(X,Y) = \frac{Cov(X,Y)}{SD(X)SD(Y)}\Leftrightarrow 
>$$
>$$
>Cov(X,Y) = Corr(X,Y)SD(X)SD(Y).
>$$
#### Bivariat normalfordeling
>[!info] Standard bivariat normalfordeling
>$X$ og $Y$ har standard bivariat normalfordeling med korrelation $\rho$ hvis og kun hvis
>$$
>Y=\rho X+\sqrt{ 1-\rho^2 }Z,
>$$
>hvor $X$ og $Z$ er uafhænige standard normal variable.