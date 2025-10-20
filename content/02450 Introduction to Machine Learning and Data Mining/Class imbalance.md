# Class imbalance problem

> Lecture 9 – 31/10/23
> 
> Chap. 16

###### Motivation

Data sats might have imbalanced class distribution

Example: Defect occur rarely (1/1,000,000)

Danger: Algorithm that never classify defect is 99.999% correct.

### Resampling balanced data

###### Approaches:

- Undersampling

- Oversampling

- Somewhere in between

![Skærmbillede 2023-10-31 kl. 14.21.45.png](/var/folders/sq/wx9hvn512t98113z7jvv2j7m0000gn/T/TemporaryItems/NSIRD_screencaptureui_HaPTVQ/Skærmbillede%202023-10-31%20kl.%2014.21.45.png)

### Precision and recal

##### Confusion matrix

|            |          |          | Predicted |
| ---------- | -------- | -------- | --------- |
|            |          | Positive | Negative  |
|            | Positive | **TP**   | **FN**    |
| **Actual** | Negative | **FP**   | **TN**    |

###### Precision

$$
p = \frac{TP}{TP+FP}
$$

###### Recall

$$
r = \frac{TP}{TP+FN}
$$

### Receiver operating characteristic

Threshold is usually 0.5 but can be changed between 0 and 1 (models predicted probability that a point belongs to a certain class)

![Skærmbillede 2023-10-31 kl. 14.38.50.png](Skærmbillede%202023-10-31%20kl.%2014.38.50.png.md)

$$
TPR = \frac{TP}{TP + FN}
$$

$$
FPR = \frac{FP}{TN + FP}
$$

<img title="" src="file:///Users/bertramhage/Desktop/Skærmbillede%202023-10-31%20kl.%2014.41.35.png" alt="Skærmbillede 2023-10-31 kl. 14.41.35.png" data-align="center" width="263">
