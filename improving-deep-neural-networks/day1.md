### 1.1 Setting up your ML application   \(Train/dev/test sets\)

##### Applied ML is a highly iterative process
 
  - \# of layers 
  - \# of hidden units 
  - learning rates
  - what activation functions used for different layers 
 
Area: NLP, Vision, Speech, Structured data(ads, search, security, logistic...)
  
Idea -> code -> Experiment -> Idea

##### Train/Dev/Test Sets
1. 60/20/20 in old times when data is quite small (100)
2. Now in big data era, 
  - The `dev sets` goal is to test which algorithm works better
  - The main goal of your `test set` is, given your final classifier to give you a pretty confident estimate of how well it's doing
  - So if we have a 1,000,000 data, we need just 10,000 for dev and 10,000 for testing, the ratio should be `98/1/1`
  - For data more than 1 million, we can use 99.5/0.25/0.25
  
##### Mismatched train/test distribution 
Examples:

|Set type| Desc |Features|
|---------|---|---|
|Training|Cat pictures from webpages|Hight resolution, nicely framed pictures|
|Dev/test|Cat pictures from users using your app |blurrier, lower res images|

⚠ Make sure the dev and test come from same distribution 

- But deep learning training requires huge amount of data, you might use all sorts of creative tactics such as crawling webpages, so the dev set and test set may not come from same distribution, but if they do, the progress in machine learning algorithm will be faster. 
- Not having a test set might be Ok
  - Just train different models on you training sets
  - evaluate these models with dev sets, dev sets also called test sets in this situation 
  

##### Conclusion 
 1. Having set up a train dev and test set will allow you to integrate more quickly 
 2. Allow you to more efficiently measure the bias and variance of the algorithm 
 3. Be more efficient select ways to improve the algorithm 
  
  
### 1.2 Bias/Variance
- High bias: under fitting 
- high variance: over fitting 

![](/assets/Screen Shot 2018-03-03 at 11.44.28 PM.png)
![](/assets/Screen Shot 2018-03-03 at 11.44.40 PM.png)
** The purple line represent the high bias and high variance output**

Example: Cat classification

|Train set error|Dev set error|Type|
|---|---|---|
|1%|11%|High variance, **unfitting the dev set data** |
|15%|16%|High bias, **unfitting the training set data**|
|0.5%|1%|low bias and low variance|

Under the assumption that human level performance gets nearly 0% error or more generally, that the optimal error, called Bayes error, which is nearly 0%

##### Conclusion 
By looking at the algorithm error on training set and dev set, you can diagnose whether it has high bias or high variance, or both, or maybe neither.

### 1.3 Basic "recipe" for machine learning 

high bias(Training set performance) 
|
V
Bigger network, train longer 
|
V
high variance (Dev set performance)
|
V
More data, regularition, (NN Architecture)
|
V
Done
 
##### Conclusion 
Training a NN can reduce both variance and bias, without worrying about increasing the other, the main cost of training a neural network that's too big is that computational time

### 1.4 Regularizing your neural network

##### Solution to reduce high variance
1. Adding regularization will help to prevent overfitting, or to reduce the errors in network
2. Get more training data

##### How regularization works
L2 Regularization 
- Logistic regression: 
 - Try to minimize the cost function J, some of the training examples of the losses of the individual predictions in the different examples, w and b are parameters
 - w is an x-dimensional parameter vector, and b is a real number
 - lambda: regularization parameter, hyper parameter need to tune 
 
 (⚠️ Notice: Lambda is a reserved keyword in python, so we use lambd to represent the lambda regularization parameter)
 
 
- Neural network 
  - Cost function: sum of losses 
  - Forbenius norm: Means the sum of square of elements of a a matrix
  - L2 regularization is also called weight decay
  

### 1.5 Why regularization reduces overfitting

##### How does regularization prevent overfitting?









