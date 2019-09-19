Q. What is difference between memorization and learning. If a code remembers wikipedia and is able to search through it, has it achieved learning?
    - machine is said to learn from experience E, with respect to some task T, and some performance measure P, if its performance on T, as measured by P, improves with E.

# Supervised learning
<b>Some popular supervised learning algorithms (covered in this
book)</b>:
- k-Nearest Neighbors
- Linear Regression
- Logistic Regression
- Support Vector Machines (SVMs)
- Decision Trees and Random Forests
- Neural networks

# Unsupervised learning
<b>Some popular unsupervised learning algorithms (covered in this
book)</b>:
- Clustering
    - k-means
    - Hierarchical cluster analysis
    - expectation maximization
- Visualization and dimensionality reduction
    - principle component analysis (PCA)
    - Kernal PCA
    - locally-linear embedding (LLE)
    - t-distributed stochastic neighbor embedding (t-SNE)
- Anomaly detection
- Association rule learning
    - Apriori
    - Eclat

# Reinforcement learning
Learning system, called an **agent**, can **observe** the environment, select and perform **actions**, and get positive or negative **rewards**. It must learn on itself what is the best strategy, called a **policy**, to get the most reward over time.

# Batch or online learning
1. Batch learning
    - first system is trained, and then it is lauched into production and runs without learning anymore.
1. Online learning
    - system learns in deployment from incoming data.

# Instance based versus model based learning
1. Instance based system memorizes all the samples and then generalizes using some similarity based measurement.
1. Model based system on the other hand uses the samples to build a model and uses it to generalize to new examples.

# Main challenges of machine learning
1. Insufficient quantity of training data
1. Non representative data
    - sampling noise 
    - sampling bias
1. Poor quality data: errors in data, missing values, etc.
1. Irrelevant features: 
    - feature selection
    - feature extraction
    - creating new features
1. Overfitting
    - model learns patterns in training data that is not relevant to the output. This learning reduces training error but not test since noise in training does not generalize to test.
    - Regularization constraints the model to be simpler [o/p if we are training a two degree polynomial model with $\ell_2$ regularization on a data that is truely linear, it will keep exchanging the mass from second coefficient to the first one even if the loss function (without regularization part) does not reduce or even increases if overall loss reduces due to reducing value of weight, i.e., simpler model. On other hand if there is no regularization it will pick any pair of values that fits the data.]
1. underfitting
    - too simple to learn underlying structure in data.


# Testing and Validating 
1. k-fold cross validation
