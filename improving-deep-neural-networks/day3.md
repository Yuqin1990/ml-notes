
### 1.11 Weight initialization for deep networks

##### Single neuron example
- 4 input x1, x2, x3, x4
- a = g(z)
- z = w1x1 + w2x2 + w3x3 + w4x4 ... + wnxn
- The larger n is, the smaller wi is, thus the z will be smaller
- One reasonable thing to do would be to set the variance of Wi to be equal to 1/n
- n is the number of input features that's going into a neuron 
- w[l] = np.random.randn(shape) * np.sqrt(1/n[l-1])
- RelU activation function g\[l\](z) = ReLU(z)

![](/assets/Screen Shot 2018-03-05 at 11.00.01 PM.png)


### 1.12 Numerical approximation of gradients 
> Gradient checking make sure the implementation of back-propagation is correct

##### Numerically approximate computations of gradients
- Checking your derivative computation
- Two-sided difference formula is much more accurate
    - set Theta 
    - set (Theta - epsilon) and (Theta + epsilon)
    - height = f(theta + epsilon) - f(theta - epsilon)
    - width = 2 * epsilon
    - g(theta) roughly equals to height/width
    - g(theta) = 3 \* (theta \** 2) = 3 
    - Theta = 1, epsilon = 0.01, g(theta) = 3.0001
    - The approximation error is 0.0001, can be represent as O(epsilon \ ** 2)
- Conclusion 
    - g(theta) is probably a correct implementation of the derivative of f
 ![](/assets/Screen Shot 2018-03-05 at 11.14.25 PM.png)   

### 1.13 Gradient Checking
- Step1: Take all w and b and reshape into a big vector theta
- Step2: take dw and db and reshape into a big vector dtheta 

##### Implementation of gradient checking 
1. For each i, calculate dtheta, use two-sided difference
2. Result of 1 should approximately equal to dtheta[i], which is supposed to be the partial derivative of J or of respect to dtheta
![](/assets/Screen Shot 2018-03-05 at 11.30.21 PM.png)
![](/assets/Screen Shot 2018-03-05 at 11.30.32 PM.png)


### 1.14 Pratical tips of implementing Gradient Checking

- Don't use in training - only to debug 
    - compute dtheta approx[i] is a slow computation, it's much too slow
- If algorithm fails grad check, look at components to try to identify bug. 
    - d theta approx that are very different than the values of d theta 
    - If you find that the values if theta or d theta, they're far off, all correspond to dbl for some layer or for some layers, but the components for dw are quite close(different components of theta correspond to different components of b and w ), the bug in how you're computing db, the derivative with respect to parameters b
- Remember regularization
- Doesn't work with dropout
    - dropout can be viewed as optimizing some cost function J, J is too large to compute, and you just sampling the cost function every time you eliminate different random subsets in those that we use dropout, so it's difficult to use grad check to double check your computation with dropouts, **set keep-prod = 1 when debugging with grad check**
- 









