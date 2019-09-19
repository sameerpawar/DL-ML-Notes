# C2W2L01-02: Mini Batch Gradient Descent
1. GD:
    - apply update to parameters after one pass through entire training data.
    - slow
1. Mini batch
    - apply updates to parameters after one pass on a mini batch.
    - mulitple updates in one epoch (pass through training data)
    - size $m$ of mini batch **_hyper-parameter_**
        - m = M, batch GD
        - m = 1, SGD
        - smaller size of m results in noise in gradient direction and hence results in slight regularization. This is more true if in addition to mini batch GD we also perform batch normalization.

# C2W2L03-04-05: Exponentially weighted averages
1. $V_t = \beta V_{t-1} + (1-\beta)\theta_t$
    - $\lim_{\epsilon\rightarrow 0} (1-\epsilon)^{1/\epsilon} \rightarrow e^{-1}$. Thus exponential weighted averages are over ~ $1/(1-\beta)$ samples, where $\epsilon = 1-\beta$.
1. This is an memory and compute efficient way of averaging over a sliding window of $1/(1-\beta)$ samples.
1. Bias correction is needed for the initial average samples, since moving average is initialized with 0. 
    - $\hat{V}_t = V_t/(1-\beta^t)$


# C2W2L06: Gradient descent with momentum
Update equations for parameter vector $w$ are as follows

momentum: $m_t = \beta_1 m_{t-1} + (1-\beta_1)g_t$, where $g_t$ is gradient vector w.r.t $w$

bias-corrected: $\hat{m}_t = m_{t}/(1-\beta_1^t)$

update: $w_t = w_{t-1} - \alpha \hat{m}_t$, where $\alpha$ is learning rate.

# C2W2L07: RMS prop
Update equations for parameter vector $w$ are as follows

second-moment: $s_t = \beta_2 s_{t-1} + (1-\beta_2)g_t^2$, where $g_t$ is gradient vector w.r.t $w$ and square operation is element wise.

bias-corrected: $\hat{s}_t = s_{t}/(1-\beta_2^t)$

update: $w_t = w_{t-1} - \alpha g_t/(\sqrt{\hat{s}_t} + 10^{-8})$


# C2W2L08: Adam
Combines momentum and RMS prop. Update equations for parameter vector $w$ are as follows

first-moment: $m_t = \beta_1 m_{t-1} + (1-\beta_1)g_t$, where $g_t$ is gradient vector w.r.t $w$

bias-corrected: $\hat{m}_t = m_{t}/(1-\beta_1^t)$

second-moment: $s_t = \beta_2 s_{t-1} + (1-\beta_2)g_t^2$, where $g_t$ is gradient vector w.r.t $w$ and square operation is element wise.

bias-corrected: $\hat{s}_t = s_{t}/(1-\beta_2^t)$

update: $w_t = w_{t-1} - \alpha \hat{m}_t/(\sqrt{\hat{s}_t} + 10^{-8})$

# C2W2L10: Local optima, saddle points and plateaus

1. Local optima requires all dimensions to be minimal within a local neighborhood of a given point. Typical problem in low dimensional space, i.e., 2 or 3 dimensions.
1. In high dimensional spaces it is more likely to have saddle point, where surface has zero derivative but local neighborhood consists of mixture of maximas and minimas across various dimensions.
1. Plateaus is a real problem at high dimenional optimization problem
    - region where derivative is zero for long range of values so learning slows or stops.
    - momentum based methods can push the optimization across plateaus due to their memory.


