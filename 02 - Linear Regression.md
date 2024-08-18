# Prerequisites
- m : number of training samples
- x : input variable, features variable
- y : output variable, target variable
- (x, y) : an individual sample
- $(x^{(i)} , y^{(j)})$ : sample number $i$ 

# Regression
in linear regression , you can recognize if a problem is in regression kind if :
- you can predict the result according to input
- you have continuous value
# hypothesis function
an imaginary function which is our target function . we cannot reach it in reality but we can achieve a good estimation of it .
### $$h(x) \to  y$$
the simplest function in math is a linear function (which has a degree of n and n is ***not*** 0) .
so the simplest hypothesis function  is :
### $$h _ {\theta}(x) \to \theta _ 0 \ +\ \theta _ 1(x)$$
> [!IMPORTANT] No Thetas but Parameters !
> from now on , instead of thetas , we say parameters .

# Cost function
indicates how much bad is a hypothesis function between other hypothesis functions .
### $$J(\theta_0,\theta_1)={1 \over 2 } \sum^{m} _ {i=1} \left(h _ {\theta} \left(x^{(i)}\right) - y^{(i)} \right)^{2}$$
## Our Goal
find a set of thetas to minimize the $J(\theta_0,\theta_1)$ function .
### $$\underset{{\theta _ 0}, {\theta _ 1}}{\text minimize} \ J(\theta _ 0, \theta _ 1)  $$

# simple cost function $(\theta_0=0)$
our hypothesis function with $\theta=0$ will be .
### $$\theta_1=1 \to h_\theta(x)=x$$
so our cost function be like :
### $$J(\theta_1)$$
proof :
### $$J(\theta_0,\theta_1)= {1 \over 2 } \sum^{m} _ {i=1} \left(h _ {\theta} \left(x^{(i)}\right) - y^{(i)} \right)^{2}$$
### $$={1 \over 2 } \sum^{m} _ {i=1} \left(x^{(i)} - y^{(i)} \right)^{2}={1 \over 2 } \sum^{m} _ {i=1} \left(0 \right)^{2}=0$$












