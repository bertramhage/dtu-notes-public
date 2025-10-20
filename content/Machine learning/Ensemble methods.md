# Ensemble methods

> Lecture 9 – 31/10/23
> Chap. 17

**Combining multiple (weak) classifiers into one (strong) classifier**
Each classifier is trained using different variations of data sets, input attribute, classlabels and/or algorithms.

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-31%20kl.%2013.23.53.png" alt="Skærmbillede 2023-10-31 kl. 13.23.53.png" data-align="center" width="415">

###### Motivation

Can improve classification algorithms in terms of better classification accuracy, increased stability, reduced variance and less overfitting.

Given $T$ independedant classifiers for binary classification each with accuracy $p$ the probability a classifier which use majority voting is correct is given by:

$$
P(\text{Majority voting is correct}) = \sum_{t=\lceil T/2\rceil}^T P(\{ t \text{ classifiers are correct} \})
$$

$$
=\sum_{t=\lceil T/2\rceil}^T\begin{pmatrix}T\\t\end{pmatrix}p^t(1-p)^{T-t}
$$

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-31%20kl.%2013.17.44.png" alt="Skærmbillede 2023-10-31 kl. 13.17.44.png" data-align="center" width="379">

### Baggin

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_ZRxPsN/Skærmbillede%202023-10-31%20kl.%2013.20.21.png" alt="Skærmbillede 2023-10-31 kl. 13.20.21.png" data-align="center" width="511">

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_bg00MH/Skærmbillede%202023-10-31%20kl.%2013.21.46.png" alt="Skærmbillede 2023-10-31 kl. 13.21.46.png" data-align="center" width="486">

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_mqT7Wt/Skærmbillede%202023-10-31%20kl.%2013.22.38.png" alt="Skærmbillede 2023-10-31 kl. 13.22.38.png" width="391" data-align="center">

### Boosting

Try to sample points that wasn't classified correctly in the previous classifier more in the next training.

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_x60sCh/Skærmbillede%202023-10-31%20kl.%2013.24.44.png" alt="Skærmbillede 2023-10-31 kl. 13.24.44.png" width="466" data-align="center">

##### AdaBoost

> Chap. 17.4.1

$$
\begin{aligned}
& \text { Algorithm 6: AdaBoost algorithm } \\
& \text { 1: Initialize } w_i(1)=\frac{1}{N} \text { for } i=1, \ldots, N \\
& \text { 2: for } t=1, \ldots, T \text { do } \\
& \text { 3: } \quad \text { Create } \mathcal{D}_t \text { by sampling (with replacement) from } \mathcal{D} \text { according to } \boldsymbol{w}(t) \\
& \text { 4: } \quad \text { Let } f_t \text { be the classifier trained on } \mathcal{D}_t \\
& \text { 5: } \quad \epsilon_t=\sum_{i=1}^N w_i(t)\left(1-\delta_{f_t\left(\boldsymbol{x}_i\right), y_i}\right) \text { (weighted error of } f_t \text { on all data). } \\
& \text { 6: } \quad \alpha_t=\frac{1}{2} \log \frac{1-\epsilon_t}{\epsilon_t} \\
& \text { 7: } \quad \text { For each } i \text { update weights using eq. (15.7): } \\
& \qquad w_i(t+1)=\frac{\tilde{w}_i(t+1)}{\sum_{j=1}^N \tilde{w}_j(t+1)}, \quad \tilde{w}_i(t+1)= \begin{cases}w_i(t) e^{-\alpha_t} & \text { if } f_t\left(\boldsymbol{x}_i\right)=y_i \\
w_i(t) e^{\alpha_t} & \text { if } f_t\left(\boldsymbol{x}_i\right) \neq y_i .\end{cases} \\
& \text { 8: end for } \\
& \text { 9: } f^*(\boldsymbol{x})=\arg \max _{y=1,2} \sum_{t=1}^T \alpha_t \delta_{f_t(\boldsymbol{x}), y} \text { (Majority voting classifier) }
\end{aligned}
$$

Using AdaBoost:

<img title="" src="file:///var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_v0cpaW/Skærmbillede%202023-10-31%20kl.%2013.41.08.png" alt="Skærmbillede 2023-10-31 kl. 13.41.08.png" data-align="center" width="248">

### Random forest

Bagging consisting only of decision trees. 

Features for each tree is randomly selected.

A large number of trees are generated and the trees are combined using  
majority voting (bagging).
