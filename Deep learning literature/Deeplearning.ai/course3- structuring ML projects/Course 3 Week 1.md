
---
# C3W1L02
---

## Orthogalization
1. Orthogonalization of kobs help keep different objectives independent.
1. Early stopping affects two things training loss and validation loss simultaneously, hence preferred not to rely on.

## Chain of assumptions for ML
1. Fit training set well on cost function
    - application dependent, e.g., Human level performance for image classification       
1. Fit dev set well on cost function
1. Fit test set well on cost function
1. Performs well in real world

---
# C3W1L03: Single Number Evaluation Metric
Helps compare and choose decisions that improve performance. For instance, it is quite difficult to compare two algorithms using two metrics Precision and Recall separately. Instead if we combine them in one metric, such as F1-score, then we can easily choose algorithm that performs better on F1-score.

---
# C3W1L04: Satisficing and Optimizing metrics
Running time is a satisficing metric, while accuracy can be an optimizing metric.

---
# C3W1L05-L06-L07: Dev/Test sets and size
1. Dev set and test set should come from the same distribution, i.e., same group of cities rather than from disjoint regions.
1. Dev/Test set helps evaluate the generalization performance of the network, so size should be just enough for the task, e.g., 500-1k-2k
1. Dev/Test set should better reflect the real world tasks, before investing time to do better on dev/test set.

---
# C3W1L08-L09-L10: Bias-Variance, Human level Performance and avoidable bias
1. Humans are good at certain tasks. So as long as ML performance is worse than Humans, you can:
    - get more labeled data from humans.
    - gain insight from manual error analysis
    - better analysis of Bias/Variance.
1. Bias or variance is defined w.r.t to Bayes optimal error, for computer vision tasks humans are pretty good proxies for Bayes optimal error. 
1. Avoidable Bias is gap between Bayes error and training error.


---
# C3W1L12: Improving Model Performance:

## Two fundamental assumptions of supervised learning
1. you can fit the training set pretty well
    - achieve low avoidable bias
        - train a bigger model
        - hyperparameter tunning: train longer/better optimization algorithms such as Adam, rmsprop, momentum, etc.
        - different network
1. Training set performance generalizes pretty well to the dev/test set
    - achieve low variance
        - get more data
        - regularization: L2, dropout, data augmentation
        - 













