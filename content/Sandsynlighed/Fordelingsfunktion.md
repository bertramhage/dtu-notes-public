s# Fordelingsfunktioner

#### Repetition

$X$: Kontinuerte stokastiske variable $X \in \mathbb{R}$.

$$
P(a ≤ X ≤ b) = \int_a^b f(x) dx, \int_{-\infty}^\infty f(x)dx=1
$$

##### Overlevelsesfunktion

$$
P(X>x) = \int_{-\infty}^\infty f(t)dt=G(x)
$$

##### Hazardfunktion

$$
\lambda(t)=\frac{f(t)}{G(T)}, G(t)=e^{-\int_0^t\lambda(u)du}
$$

### Fordelingsfunktion

Indføres for **alle** stokastiske variable $X$

$$
F(x)=P(X≤x)= \int_{-\infty}^x f(t)dt = 1-G(x)
$$

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-13%20kl.%2010.27.29.png" alt="Skærmbillede 2023-10-13 kl. 10.27.29.png" width="311" data-align="center">

###### For diskrete fordelinger

$$
F(x) = \sum_{n=-\infty}^xP(X=n)
$$

#### Fraktiler

Generelt: $p$-fraktilen $f_p$ er givet ved

$$
P(X≤f_p)=p
$$

##### Simulering af stokastiske variable

Givet en kontinuert voksende fordelingsfunktion $F$ kan vi sample en stokastisk variabel $X$ med fordelingsfunktionen $F$

$$
X=F^{-1}(U),
$$

hvor $U$ er en uniform fordeling på $[0,1]$.

Dvs. $x$ er $u$-fraktilen i $F$.

<details>
<summary>Kan fx bruges til</summary>
<ul>
    <li> Matlab genererer tilfældige tal mellem 0 og 1 med rand</li>
    <li>Transformation med -1/lambda ln(U)</li>
    <li>Lav histogram over disse</li>
    <li>Tilsvarende histogram over variable genereret med exprnd</li>
</ul>
</details>

### Fordeling af maximum og minimum

###### Spørgsmål som

- Hvor høj er den højeste i en gruppe?

- Hvornår punkterer det første dæk?

- Hvad er den største bølgehøjde en bro vil blive udsat for?

- Største fil på hjemmeside

- Hvornår kommer den sidste, der skal med på skituren?

##### Fordelingsfunktionen for maksimum

$$
X_i, i = 1, ..., n, F_i(X)=P(X_i≤x)\\
\bar{X} = \frac{\sum_{i=1}^n X_i}{n}
$$

$$
X_{max}: \text{Værdien af den største blandt n}\\
X_{max} = \max_{1≤i≤n}{X}, 1≤i≤n\\
F_{max}(x)=P(X_{max} ≤ x) = (\max_{1≤i≤n}{X}≤x)\\
=P(X_1≤x,X_2≤x, ..., X_n≤x) =^{(Uaf)} \Pi_{i=1}^n P(X_i≤x)\\
= \Pi_{i=1}^n F_i(x)=^{(F_i(x)=F(x))}F(x)^n
$$

<details>
<summary>Eksempel</summary>
To terningekast.<br>
Chancen for 6,6 er 1/36<br>
Chancen for Xmax ≤ 2 er 4/36, (1,1), (1,2), (2,1), (2,2)<br>
Altså P(Xmax≤2) = (2/6)^2
</details>

##### Fordelingsfunktionen for minimum

$$
X_i, i=1,..., n, F_i(x) = P(X_i≤x)
$$

$$
F_{min}(x)=1-(1-F(x))^n
$$

#### Eksempel

Trækstyrke af kæde

$X_i$ : Trækstyrke af led $i$

$$
P(X_i>x) = 1-\frac{1}{2}x^2
$$

$X$: Trækstyrke af kæde

$$
X=\min_{1≤i≤n}X_i
$$

$$
P(X>x) = (1-\frac{1}{25}x^2)^n
$$

Vi antager at trækstyken for hele kæden skal være mindst $\frac{1}{10}$kg med en sandsynlighed på mindst $0.95$.

$$
P(X>\frac{1}{10}) ≥ 0.95
$$
