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

![](/assets/Screen Shot 2018-02-19 at 22.54.35.png)

- Circle represent two steps:
    1. z = wx + b
    2. a = sigmoid(z)

- Subscript represent node index

#### 3.4  Vectorizing across multiple examples

Given m training examples, for the ith(i > 2) layer:
- input: last layer output 
- apply formula:
  - z = wx + b
  - a = sigmoid(z)


Notations:
- Square brackets i: layer i
- Round brackets i: training example i



