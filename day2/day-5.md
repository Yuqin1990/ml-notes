#### 3.1 Neural Network Overview
![](/assets/Screen Shot 2018-02-19 at 22.18.11.png)

- Logistic regression
- Backward calculation 

#### 3.2 Neural Network Representation 

![](/assets/Screen Shot 2018-02-19 at 22.29.38.png)

2 Layer NN (input layer is ignored)
- Input layer - vector x
- Hidden layer (Params w and b)
- output layer - y-hat predict value (params w and b)

#### 3.3 Computing a neural network output

Repeat logistic regression computation 

![](/assets/Screen Shot 2018-02-19 at 22.54.30.png)


![](/assets/Screen Shot 2018-02-19 at 23.14.52.png)


- Circle represent two steps:
    1. z = wx + b
    2. a = sigmoid(z)

- Subscript represent node index

#### 3.4  Vectorizing across multiple examples
![](/assets/Screen Shot 2018-02-19 at 23.14.52.png)

Given m training examples, for the ith(i > 2) layer:
- input: last layer output 
- apply formula:
  - z = wx + b
  - a = sigmoid(z)

Notations:
- Square brackets i: layer i
- Round brackets i: training example i

#### 3.5 Explanation for vectorized implementation 
![](/assets/Screen Shot 2018-02-19 at 23.16.02.png)

- Simplify the justification, ignore b, b = 0
- wx(i) should get a column vector
- z[i]: one column corresponds to one example z value at ith layer

![](/assets/Screen Shot 2018-02-19 at 23.16.09.png)

For multiple layer NN, just do the two steps repeatly. 

#### 3.6 One hidden layer NN - Activation function 

![](/assets/Screen Shot 2018-02-19 at 23.44.56.png)

- Use g(z) represent activation function 
- Sigmoid function is an activation function
- tanh function, the hyperbolic tangent function, range from -1 to 1. centered 0, if z is too large or too small, the slope would be very small
- **tanh function always works better than sigmoid function**, because the mean is close to 0, has the effect of centering the data
- activation function can be different in different layer 
- use square bracket to represent different layer 

![](/assets/Screen Shot 2018-02-19 at 23.41.05.png)

Pros and cons:
- sigmoid function: never use it except for the output layer if you are doing binary classification 
- tanh function: always works better than sigmoid function
- reLu function: default one
- leak reLu function: a = max(0.01z, z)


  




 


