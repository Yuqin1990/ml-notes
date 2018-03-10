### 3.1 Tuning process 
##### Tips for how to systematically organize your hyperparameter tunning process
- Problems when training data, many hyperparameters 
    - Learning rate alpha 
    - Momentum beta 
    - Adam optimization params beta_1, beta_2, epsilon 
    - Number of layers 
    - Number of hidden units for each layer
    - Learning rate decay
    - Choose mini-batch size

|Hyper parameters|Importance|
|-|-|-|
|Learning rate alpha|Most|
|Momentum beta|Secondary|
|Adam optimization params beta_1, beta_2, epsilon|0.9, 0.999, 10^(-8), <br /> never tunned|
|Number of layers|Third|
|Number of hidden units for each layer|Secondary|
|Learning rate decay|Third|
|Choose mini-batch size|Secondary|

##### How to tune
>In old times, systematically explore all the hyper parameters, pick which one works best, and this practice works ok when the number of hyperparameter was relatively small 

In deep learning, 

- choose the points at random, try these points randomly, cause hard to know in advanced which hyperparameters are going to be the most important for your problem.

An example:
Hyperparamter 1: alpha 
Hyperparamter: epsilon 
epsilon doesn't have any effect on the result, while alpha matters a lot. 

- Another common practice is to use a coarse to fine sampling scheme

For example:
1. Find a point that has good result, then zoom in to a smaller region of the hyperparamters and then sample more density within this space, again randonly, but more importantly, focus on this area, the pick whatever value that allows you to do best on your training set objective or does best on your development

##### Conclusion 
- Use random sampling and adequate search 
- optionally consider implementing a coarse to fine search process

### 3.2 Using an appropriate scale to pick hyperperameters
##### Picking hyperparameters at random 



























