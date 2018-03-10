# Hyperparameters tunning 
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

- Use uniform scale 
    - Number of hidden units(50 to 100), number of layers(2 to 4), these paramters can be **uniformaly randomly** picked, but this is not true for some other hyper parameters 

- Use log scale 
    - If you searching for the hyperparameter, pick from 0.0001 to 1, and sample values uniformly at this range, assume that the most optimal point is 0.1, so you waste 90% time to search for this point. Instead, it seems more reasonable to use log scale(0.0001, 0.001, 0.01, 0,1) instead of a linear scale  
    - In python, you can implement this by **r = -4 * np.random.rand()** where r is from -4 to 0, **alpha = 10^r** where alpha is from 0.0001 to 1
$$
10^a....10^b
$$
    - In conclusion, range from 10^a(low value) to 10^b(high value), pick r uniformly randomly from a to b, this is how you implement random sampling in this log scale 

- Hyperparameters for exponentially weighted averages  
    - For example, beta is from 0.9, 0.999
        - 0.9 is like averaging last 10 values, while 0.999 is like averaging last 1000 values
        - explore range value of 1-beta (0.1 - 0.001) 
        - we can use log scale, so r is from -3 from -1
   - Another disadvantage for sampling on a linear scale is that when beta is close to 1, the sensitivity of the results that you get changes even with small changes with beta, if beta changes from 0.9000 to 0.9005, you changes won't be changed. but if beta is from 0.999 to 0.9995, this will have a huge effect on your result. **So this cause you to sample more densely when bet close to 1** 
   
### 3.3 Hyperparameters tuning in practice Panda vs. Caviar
>Tips and tricks of how to organize your search hyperparameter process

##### Re-test hyperparameters occasionally 
Deep learning has been applied into many areas, and the algorithm in one area may or may not transfer to a different one. There is a lot of cross-fertilization, rest-net which developed in computer vision area successfully applied to speech area as well
- For hyperparameters, you need to retesting or reevaluating your hyperparamters
    
##### Babysitting one model 
Given that you have a huge data set, but not a lot of computational resources, not a lot of CPUs and GPUs, in this case, you can gradually babysitting your model step by step
2 Approach:

** Approach 1 ** 
>Like panda, have one baby and babysitting it

1. On day 0, you might initiate params randomly and start training, and gradually watch your cost function J, data set error falls down. Then you may try to increase your leaning rate, and may be it does better, 
2. After 2 days, may be you can fill the momentum term a bit 
3. And every day you kind of look at it and leveraging your parameters, and maybe one day you found your learning rate too big, so you go back to previous day model 
4. In this way, you're babysitting your model over days of weeks. that's usually what happens if you don't have much computation and capacity to train a lot of models 
    - Watching the performance
    - Patiently leveraging the parameters 

** Approach 2 **
>Like Caviar, have million of children, just see that hopefully one or some of them will grow up successfully

Train multiple models at parallel, have some settings for params, and just let it run by itself, wither for day or multiple days, and below should be a plot of the cost function , cost of data set error, and your second model may generate another curve(the purple one), the third model look lik ered curve, and so on, in this way, you can try a lot of hyperparameter settings, then just quickly at the end pick the one that works best, 


##### Conlusion
If you have enough computation and resources to train multiple models in parallel, just choose Approach 2. 
But in some area such as online ad and computer vision that has so much data to train that it's difficult to train all those at the same time, these communities use Approach 1 more often. but even for approach 1. after 2 or 3 weeks, you still need to babysitting another model. 

 
 
# Batch Normalization 

### 3.4 Normalizing activations in a network 
Batch normalization make your hyperparameter search problem much easier, make the NN much more robust to the choice of hyperparameters and enables you to train a NN easier

##### Normalizing inputs to speed up learning 
- When you training a model such as logistic regression, normalizing the input features can speed up learning 
    - Compute the means, subtract off the means from your training set, compute the variance
    - Then normalize your data set according to the variance
    - This works for the input values to a netial network or to logistic regression
- For deep learning model, you much multiple input features, and you have different activation functions for different layers, so if you want to train w and b, normalize alpha will make the training process more efficient 
    - For any hidden layer, normalize the values of a, this process is called batch normalization or batch normal, but actually we are **normalize z instead of a**
    
    
##### Implementing Batch Norm
Given some intermediate values in neural net, you have some hidden unit values Z(1) up to Z(m)
    - Compute the mean and variance of z
    - Take each Z_i and normalized by the formula 
    - But we don't want the hidden units ro always have mean 0 and variance 1, **it makes sense for hidden units to have a different distribution**, so instead we compute Z_tildle, equals to gamma * z_norm + beta (gamma and beta are learnable parameters of the model)
    - Use gradient descent to update the params beta and gamma, just like updating the weights of the NN. (⚠️Notice that: It allows you to set the mean of Ztilde to be whatever you want to be )
    - By an appropriate setting of the parameters gamma and beta, this normalization step (the 4 equations) is just computing the identity function by choosing other values of gamma and beta. this allows you to make the hidden unit values of other means and variance as well. 
    - Now use z_tilde_i instead of z_i in your NN


##### Conclusion
- Normalizing the input features X can help learning in the NN. 
- Batch norm does it applied that normalization process not just to input layer, but to the values even deep in some hidden layer in the NN
- The difference between the training input and these hidden unit values is you might not want your hidden unit values to be forced to mean 0 and variance 1. 
    - For example, if the activation function is sigmoid function, you don't want your values to always be clustered here, you want them to has a large variance and a mean that is not 0 in order to better take advantage of the non-linearity of the sigmoid function rather than all the values be in just the linear version , that's why with gamma and beta you can now make sure that the Z(i) values have the range of values that you want
    
    
### 3.5 Fitting Batch Norm into a neural network 

##### Adding Batch Norm to a network
In a simple NN, You can view each of the unit as computing 2 things
    1. Compute Z
    2. Apply activation function to calculate a

- If apply Batch Norm
    1. The input X will fit into the first hidden layer, and then first compute Z1, and this is governed by the params z1 and b1
    2. Then ordinarily, you would fit Z1 into the activation function to compute a1, z will be applied batch norm, this will govern by gamma_1 and beta_2, this will give you new normalize value Z1, then fit this to the activation function to get a1, now you've done the computation for the first layer, 
    3. Then in second layer, use the Z from step 2 to compute Z2. and this is governed by w2, b2
    4. Repeat this process for each layer.    
    
(⚠️ Notice: The beta used in batch norm is different than the beta used in momentum and the Adam and RMSprop algorithm)
 
You can implement batch normalization with ```tf.nn.normalize```

##### Working with mini-batches
1. Take your first mini-batch and compute Z1
2. Compute mean and variance of this mini-batch 
3. Resale the Z by gamma and beta
4. Apply the activation function 
5. Repeat this in each layer
6. repeat 1-5 in each mini-batch

Params: w, b, beta, gamma
(⚠️ Notice: The way Z was computed as follows, first normalize z by mean and variance, then rescale it by beta and gamma, whatever the value of bl is actually going to just get subtracted out, because during the batch normalization step, you are going to compute the means of zl's and substract the mean, so adding any constant to all of the examples in the mini-batch **it doesn't change anything because your add will get cancelled out by the mean subtraction step**) 

Beta controls the shift and bias terms.

##### Implementing gradient descent
Just add normalization before computing a
 



    
                                                                        
  






















