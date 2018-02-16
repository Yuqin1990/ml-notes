##### 2.1 Binary Classification 
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


##### 2.2 logistic Regression
x: input, nx dimension vector
w: parameters of logistic regression, nx dimension vector
b: a real number, interceptor 
y: output 

**linear regression**
y = w \* x + b
but y should be between 0 and 1, so this algorithm can't fit the model

**logistic regression**
![](/assets/Screen Shot 2018-02-16 at 21.59.09.png)
y = sigmoid(w \* x + b)
>sigmoid function:  
-infinity: close to 0
0: 0.5
infinity: close to 1



