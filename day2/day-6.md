#### 3.7 Why do you need a nonlinear activation function 

![](/assets/Screen Shot 2018-02-20 at 20.09.38.png)

- g(z) = z linear function
- Linear hidden layer is useless because the composition of two linear functions is itself a linear function
- There is only one situation that you can use g(z) = z if you are doing machine learning on a regression problem, so y is a real number, you can use linear function for **output layer**. but **hidden layer** should not use non-linear function

#### 3.8 Derivatives of activation functions
![](/assets/Screen Shot 2018-02-20 at 20.19.21.png)
- Sigmoid activation function 
  g'(z) = g(z) * (1 - g(z))
  
![](/assets/Screen Shot 2018-02-20 at 20.19.31.png)

- tanh activation function 
  g'(z) = 1 - g(z)*g(z)
  
  ![](/assets/Screen Shot 2018-02-20 at 20.19.38.png)
  
- ReLU and leaky ReLU
  g'(z) = 0 if z < 0
  g'(z) = 1 if z > 0
  
#### 3.9 Gradient descent for NN


        
