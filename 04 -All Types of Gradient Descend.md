# Kinds of Decreasing Gradient

- with full-back : updating in each loop with all samples
- random (online) : updating in each loop with one random sample
- mini batch gradient descend : updating  in each loop with one random small batch sample

> [!IMPORTANT]
> in this lesson , when we say Gradient Descend algorithm , we mean mini batch gradient descend algorithm .

# Multi Feature linear Regression

symbols:
- n means number of features .
- $x^{(i)}$ inputs in sample number i .
- $x^{(i)}_j$ feature number j in sample number i .
- $x_0$ this variable is always equal to 0 .

our new hypothesis function :
### $$h_\theta(x)=\theta_0(x_0)+\theta_1(x_1)+\theta_2(x_2)+\dots+\theta_n(x_n)$$
### $$x=\begin{bmatrix} {\color{red}x_0=1} \\ x_1 \\ \vdots \\ x_n \end{bmatrix} \ \ \theta=\begin{bmatrix} \theta_0 \\ \theta_1 \\ \vdots \\ \theta_n \end{bmatrix} \Longrightarrow {\color{cyan}h_\theta(x)=\theta^Tx}$$ 
> [!IMPORTANT]
> $\theta^Tx$ means dot product or "ضرب داخلی" .

# Multi Feature Gradient Descend

multi parameter hypothesis function :
### $$h_\theta(x)=\theta^Tx = \theta_0+\theta_1x_1+\theta_2x_2+\dots+\theta_nx_n$$

parameters :
### $$\theta=(\theta_0,\theta_1,\dots,\theta_n)$$
cost function :
### $$J(\theta_0,\theta_1,\dots,\theta_n)={1\over2}\sum^{m}_{i=1}\left( h_\theta(x^{(i)}) - y^{(i)} \right)^2$$
### $${\partial \over \partial\theta_j}J(\theta)= \sum^{m}_{i=1}\left( h_\theta(x^{(i)}) - y^{(i)} \right).x^{(i)}_j$$

### `repeat until convergence {`
### $\ \ \ \ \ \theta_j := \theta_j - \alpha{\partial \over \partial\theta_j}J(\theta)$ 
### `}`


# In-Practice Tricks in Multi Parameter Regression

- ### Scaling Parameters
- ### Defining Learning Rate 

## Scaling Parameters

Idea : assurance of parameters be in a similar scale .
goal : increasing convergence speed in gradient descent .

### statistics normalizing formula

$range = \text{end of period} -  \text{start of period}$ 
$size = \text{current x to normalize}$
$average = \text{statistics average}$

### $$x = {x - average \over range}\ | -0.5\leq x \leq0.5$$or :

#### $\mu_j = \text{average}$
#### $\sigma_j= \text{scattering}$
### $$x_j={x_j-\mu_j \over \sigma_j}$$

## Defining Alpha

- convergence test

### convergence test

convergence happened if $J(\theta)$ value changes less than $10^{-3}$ in a single repeat of loop .

> [!IMPORTANT] it's correct !
> definitely you are minimizing a cost function , in gradient descent algorithm when you are solving a machine learning problem . and you can assure you are solution is correct when you draw a diagram and see if the $J(\theta)$ output must be decreasing and become convergent after a while .

> [!DANGER] it's incorrect !
> and if you are looking at a divergent $J(\theta)$ diagram , definitely you made a mistake .

# Hyper parameters and parameters

we call $\theta_n$ as parameter , and we call $\alpha$ as hyper parameter .

# Normal Equation


# summary
- learning rate:
	- too small : too much slow convergent
	- too big : slow convergent or failure in convergence
- choosing learning rate
	- pick 






