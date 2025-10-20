# Performance evaluation

**Goal**: to examine the difference in the generalization error $z_D$ defined as:

$$
z_D = E_{D, A}^{gen} - E_{D, B}^{gen}   
$$

If    $z_D<0$ that means model A is better than model B.

#### Hypothesis testing

Determine **whether there is an effect** by choosing between $H_0:z=0$, vs. $H_1: z \neq 0$.

##### Estimation

Determine a likely value $z \approx \hat{z}$ and an interval $[z_L, z_U]$ that likely containt $z$.

##### P-value

- Evidence against $H_0$ is measured by a p-value (low p is evidence for an effect $z \neq 0$ ).

- Estimation of $[z_L, z_U]$ done using an $\alpha$-confidence interval (lower $\alpha$ means a more conservative, wider, interval). 

- 
