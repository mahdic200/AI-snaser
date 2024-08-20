# Single Variable Linear Regression in a nutshell

- hypothesis : $h_\theta(x)=\theta_0+\theta_1(x)$
- parameters : $\theta_0,\theta_1$
- cost function : $J(\theta_0,\theta_1)={1\over2}\sum^{m}_{i=1}(h_\theta(x^{(i)})-y^{(i)})^2$
- target / goal function : $\underset{\theta_0,\theta_1}{minimize}\  J(\theta_0,\theta_1)$

# Training

training means : finding appropriate value of thetas according to dataset .
estimating / anticipating means : using found hypothesis function on new dataset .

# Descending Gradient

cost function :
### $$J(\theta_0,\theta_1)$$
goal function :
### $$\underset{\theta_0,\theta_1}{minimize}\ J(\theta_0,\theta_1)$$

general steps :
- start with random values for $\theta_0, \theta_1$
- decrease the $J(\theta_0,\theta_1)$ output by changing the parameters in an appropriate way .
- repeat the above steps until you reach a minimum output for cost function .

## the Algorithm

column vector :
### $$\boldsymbol{\theta} = \begin{bmatrix}\theta_0 \\ \theta_1 \end{bmatrix}$$
row vector :
### $$\boldsymbol{\theta^T} = [\theta_0,\ \theta_1]$$

### Gradient Formula
## $$\nabla J=\begin{bmatrix} { {\partial J}\over{\partial \theta_0} } \\ { {\partial J}\over{\partial \theta_1} } \end{bmatrix}$$

### Decreasing Gradient Formula

## $$-\nabla J=\begin{bmatrix} -{ {\partial J}\over{\partial \theta_0} } \\ -{ {\partial J}\over{\partial \theta_1} } \end{bmatrix}$$

### $$\boldsymbol{\theta}^{(new)}=\boldsymbol{\theta}^{(old)}+\alpha(-\boldsymbol{\nabla J})$$

### $$\begin{bmatrix} {\theta_0} \\ {\theta_1} \end{bmatrix} = \begin{bmatrix} {\theta_0} \\ {\theta_1} \end{bmatrix} + \alpha \begin{bmatrix} -{ {\partial J}\over{\partial \theta_0} } \\ -{ {\partial J}\over{\partial \theta_1} } \end{bmatrix}$$
### $$\theta_j = \theta_j - \alpha \left( \partial J \over \partial\theta_j \right)$$
> [!WARNING] SIMULTANEOUSLY !
> all variables MUST be updated simultaneously , otherwise your algorithm won't work ! .

> [!WARNING] DON'T TAKE IT EASY !
> if you choose the learning rate $\alpha$ too big , your algorithm probably will be converged slowly or become divergent .
> and if you pick the learning rate too small , your algorithm is going to be converged slowly .

## Algorithm implementation

> [!DANGER] Incorrect !
> ### `repeat until convergence {`
> ### $\ \ \ \ \ \ \theta_j := \theta_j - \alpha{\partial \over \partial\theta_j}J(\theta_0, \theta_1)$
> ### `}`

> [!SUCCESS] Correct one
>save the Delta instead of updating parameters values .
>
> ### `repeat until convergence {`
> ### $\ \ \ \ \ \ \Delta\theta_j :=-\alpha{\partial \over \partial\theta_j}J(\theta_0, \theta_1)$
> ### `}`


# Convergent

is going to be like this . when your gradient stuck in a local minimum , convergent will happen and that's mean your algorithm found an answer for $J(\theta_j)$ function .
### $${\partial \over \partial \theta_j}J(\theta_j) = 0$$
## Cost Function Gradient

### $$\begin{align} {\partial \over \partial\theta_j}J(\theta_0,...,\theta_j) = \\ {\partial \over \partial\theta_j} {1\over2}\sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right)^2 \end{align}$$
##### and if you consider $h_\theta(x^{(i)})=\theta_0+\theta_1x^{(i)}$ 

### $$\begin{align} = {\partial \over \partial\theta_j} {1\over2}\sum^m_{i=1} \left( (\theta_0+\theta_1x^{(i)}) -y^{(i)} \right)^2 \end{align}$$
for j = 0 .
### $$\begin{align} {\color{cyan}j=0} \Rightarrow{\partial \over \partial \theta_0}J(\theta_0,\theta_1) = \\ {\partial \over \partial\theta_0} {1\over2}\sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right)^2 = \\ 2 \times {1\over2}\sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right) \times (1+0+0) = \\ \sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right) \end{align}$$
and for j = 1 .
### $$\begin{align} {\color{cyan}j=1} \Rightarrow{\partial \over \partial \theta_1}J(\theta_0,\theta_1) = \\ {\partial \over \partial\theta_1} {1\over2}\sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right)^2 = \\ 2 \times {1\over2}\sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right) \times (0+x^{(i)}+0) = \\ \sum^m_{i=1} \left( h_\theta(x^{(i)})-y^{(i)} \right)(x^{(i)}) \end{align}$$
> [!NOTE] note !
> in linear regression , cost function is curve , and consequently , decreasing gradient will be convergent in global minimum necessarily .


















