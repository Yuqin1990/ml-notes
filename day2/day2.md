#### 2.1 Binary Classification 
![](/assets/Screen Shot 2018-02-16 at 21.30.37.png)
![](/assets/Screen Shot 2018-02-16 at 21.39.50.png)

###### Example: 
Given an image as input 
return label 1 if it is cat
return label 0 otherwise

Goal: Train a classifier that the input is an image represented by a feature vector, x, and predicts whether the corresponding lable y is 1 or 0
###### Notations:
![](/assets/Screen Shot 2018-02-16 at 21.45.24.png)

x: input feature vector
n: dimension of x, in this case, equals to 64 \* 64 \* 3 = 12288
m: # of training example 
X: an nx \* m demensional matrix
Y: m dimension matrix 


#### 2.2 logistic Regression
**Definition**
>An algorithm used in a supervised learning problem when the output y are all either 0 or 1, The goal of the logistic regression is to **minimized the errors** between its predictions and training data 


x: input, nx dimension vector
w: parameters of logistic regression, nx dimension vector
b: a real number, interceptor 
y: output 

Linear regression
y = w \* x + b
but y should be between 0 and 1, so this algorithm can't fit the model

**Logistic regression**
![](/assets/Screen Shot 2018-02-16 at 21.59.09.png)

y = sigmoid(w \* x + b)
> sigmoid function:  
> -infinity: close to 0
> 0: 0.5
> infinity: close to 1

#### 2.3 Cost function 
![](/assets/Screen Shot 2018-02-16 at 22.30.28.png)
m: # of training sets
i: ith training example
y-hat(i): The prediction on taining sample (i)
Loss function: To measure how good the output y-hat is when true label is y. (For single training example)
Cost Function: average of loss function sum. (Apply to all training samples)

#### 2.4 Gradient descent algorithm 
![](/assets/Screen Shot 2018-02-16 at 22.45.28.png)

- Cost function: convex function, looks like a bowl

- Approach: Started from random initial point, then takes a step in the steepest downhill direction, this is one iteration of gradient descent, after n iterations, finally you converge to the global optimum.

#### 2.5 Derivatives 
#### 2.6 More derivative example 
Already learned, Skipped 

#### 2.7 Computation Graph
Forward propagation step: compute the output of the neural network
Backward propagation step: compute gradients or compute derivatives

>J(a, b, c) = 3(a + bc)
step1: u = bc
step2: v = a + u
step3: J = 3v




 

