### Generalized linear model

- Data: $\quad\left\{\boldsymbol{x}_n, y_n\right\}_{n=1}^N$

- Model: $\quad f(\boldsymbol{x})=g_{\text {link }}\left(\boldsymbol{x}^{\top} \boldsymbol{w}\right)$

- Cost function: $d(y, f(\boldsymbol{x}))$

- Parameters: $\quad \boldsymbol{w}=\underset{\boldsymbol{w}}{\arg \min } \sum_{n=1}^N d\left(y_n, f\left(\boldsymbol{x}_n\right)\right)$

### Visual representation of artificial neural network

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-24%20kl.%2014.22.35.png" alt="Skærmbillede 2023-10-24 kl. 14.22.35.png" data-align="center" width="334">

Each neuron

- Computes a non-linear function of the sum of it's input

- Is just like a GLM

- Has its own set of parameters

Modeling choices

- Cost function

- Non-linearities

- Number of neurons and hidden layers

- Selection of inputs

Parameters is estimated using numerical optimization methods (of cost function)

#### Parameter fitting

Let $h^{(i)}$ be the function at the $i$'th layer. Also let $\mathbf{w}_j^{(i)}$ be the weights at node $j$ at the $i$'th layer (going from layer $i-1$ to $i$).

Data: $\{\mathbf{x}_i, y_i\}$

Model:

$$
f(\boldsymbol{x})=h^{(2)}\left(v_{10}+\sum_{j=1}^H v_{1 j} h^{(1)}\left(\tilde{\boldsymbol{x}}^{\top} \boldsymbol{w}_j\right)\right)
$$

Distance: $d(y,f(\mathbf{x}))$

Cost: $E=\sum_{i=1}^Nd(y,f(\mathbf{x}))$

###### Common choices

$$
\begin{aligned}
h^{(1)}(x) & =\tanh (x) \\
h^{(2)}(x) & =x \\
d(y, f(\boldsymbol{x})) & =(y-f(\boldsymbol{x}))^2
\end{aligned}
$$

Let $z_j^{(1)}$ be output of the $j$'th hidden unit

$$
z_j^{(1)} = h^{(1)}(\mathbf{w}_j^{(1)^T}\tilde{x})
$$

Abbriviated:

$$
\mathbf{z}^{(1)} = h^{(1)}(\mathbf{W}^{(1)}\tilde{x})
$$

###### Output

$$
f(\boldsymbol{x})=h^{(2)}\left(v_{10}+\sum_{j=1}^H v_{1 j} z_j^{(1)}\right)=h^{(2)}\left(\boldsymbol{W}^{(2)} \tilde{\boldsymbol{z}}^{(1)}\right)
$$

#### Multiple outputs

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-24%20kl.%2014.59.20.png" alt="Skærmbillede 2023-10-24 kl. 14.59.20.png" data-align="center" width="205">

Let $\mathbf{W}^{(2)}$ be a $C\times H$ matrix then:

$$
\boldsymbol{y}=\boldsymbol{f}(\boldsymbol{x})=h^{(2)}\left(\boldsymbol{W}^{(2)} \tilde{\boldsymbol{z}}^{(1)}\right)
$$

will be $C$-dimensional.

Re-define error-function:

$$
E=\sum_{i=1}^N\left\|\boldsymbol{y}_i-\boldsymbol{f}\left(\boldsymbol{x}_i\right)\right\|_2^2
$$

###### Example: 3-d output:

$$
\mathbf{y}=[o_1, o_2, o_3]

$$

#### Multiple layers

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-24%20kl.%2014.58.55.png" alt="Skærmbillede 2023-10-24 kl. 14.58.55.png" data-align="center" width="180">

Let $\mathbf{z}^{(0)}=\mathbf{x}$

For each layer $l$ compute

$$
z_j^{(l)}=h^{(l)}\left(\boldsymbol{W}^{(l)} \tilde{\boldsymbol{z}}^{(l-1)}\right)
$$

Output is 

$$
f(\mathbf{x})=\mathbf{z}^{(L)}
$$

### Gradient decent

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_6kFP51/Skærmbillede%202023-10-24%20kl.%2014.55.22.png" alt="Skærmbillede 2023-10-24 kl. 14.55.22.png" data-align="center" width="391">

Start from an initial guess of $\mathbf{w}^*$.
At step $t$ of the algorithm, modify $\mathbf{w}^{(t-1)}$ to produce a better guess $\mathbf{w}^{(t)}$.

### Multi-class classification

###### Logistic regression, $y=0,1$:

$$
\begin{aligned}
p(y|\theta)=\theta^y(1-\theta)^{(1-y)}\\
\theta = \sigma(\mathbf{x}^T\mathbf{w})
\end{aligned}
$$

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_SFyQCe/Skærmbillede%202023-10-24%20kl.%2015.06.21.png" alt="Skærmbillede 2023-10-24 kl. 15.06.21.png" width="142" data-align="center">

###### Multinomial regression, $y=1,2,...,K$

$$
z_k:\text{one-of-K encoding of }y,
$$

$$
\begin{aligned}
p(y \mid \boldsymbol{\theta}) & =\prod_{i=1}^K \theta_k^{z_k} \\
\boldsymbol{\theta} & =\operatorname{softmax}\left(\left[\begin{array}{lll}
{\left[\boldsymbol{x}^{\top} \boldsymbol{w}_1\right.} & \cdots & \boldsymbol{x}^{\top} \boldsymbol{w}_K
\end{array}\right]\right) \\
& =\left[\begin{array}{llll}
\frac{e^{\boldsymbol{x}^{\top} \boldsymbol{w}_1}}{\sum_{c=1}^K e^{\boldsymbol{x}^{\top} \boldsymbol{w}_c}} & \cdots & \frac{e^{\boldsymbol{x}^{\top} \boldsymbol{w}_{K-1}}}{\sum_{c=1}^K e^{\boldsymbol{x}^{\top} \boldsymbol{w}_c}} & \frac{e^{\boldsymbol{x}^{\top} \boldsymbol{w}_K}}{\sum_{c=1}^K e^{\boldsymbol{x}^{\top} \boldsymbol{w}_c}}
\end{array}\right] \\
\text { or: } \boldsymbol{\theta} & =\left[\begin{array}{llll}
\frac{e^{\boldsymbol{x}^{\top}} \boldsymbol{w}_1}{1+\sum_{c=1}^{K-1} e^{\boldsymbol{x}^{\top} \boldsymbol{w}_c}} & \cdots & \frac{e^{\boldsymbol{x}^{\top} \boldsymbol{w}_{K-1}}}{1+\sum_{c=1}^{K-1} e^{\boldsymbol{x}^{\top} \boldsymbol{w}_c}} & \frac{1}{1+\sum_{c=1}^{K-1} e^{\boldsymbol{x}^{\top} \boldsymbol{w}_c}}
\end{array}\right]
\end{aligned}
$$

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-24%20kl.%2015.06.38.png" alt="Skærmbillede 2023-10-24 kl. 15.06.38.png" data-align="center" width="163">
