# Order statistics

Vi har

$X_1, X_2, ..., X_n$

$X_{min} = X_{(1)}≤X_{(2)}≤...≤X_{(n)} = X_{max}$

$X_{(k)}$: Den $k$'te order statistic

$X_i$ uafhængige identisk fordelt kontinuerte med tæthed $f(x)$

$f_k(x)$: Tæthed for $X_{(k)}$

---

$$
f_k(x)=n\begin{pmatrix}n-1\\k-1 \end{pmatrix}f(x)F(x)^{k-1}(1-F(x))^{n-k}
$$

---

$$
f_n(x) = nf(x)F(x)^{n-1} \implies F_{max}(x) = F(x)^n
$$

#### Eksempel uniform

$X_i$~ Unif(0,1) fordelte

$$
f(x)=1,    F(x)=x
$$

$$
f_k(x)=n\begin{pmatrix}n-1\\k-1\end{pmatrix}x^{k-1}(1-x)^{n-x}
$$

## Multi/polynomialfordelingen

$n$ emner

$m$ kategorier

Et emne tilhører kategori $j$ med sandsynlighed $p_j$ uafhængigt af de andre emner.

Lad $N_j$ være antal emner i kategori $j$

$$
P(N_1 = n_1, N_2 = n_2, ..., N_m = n_m) = \frac{n!}{n_1!n_2!...n_m!}p_1^{n_1}p_2^{n_2}...p_m^{n_m}
$$

Lad $N_1$ være antallet af $X_i$≤x, og $N_2$ antallet af $X_i$ i intervallet $]x, x+dx]$ og endeligt $N_3$ af $X_i>x+dx$
