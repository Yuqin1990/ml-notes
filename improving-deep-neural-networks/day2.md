### 1.6 Dropout regularization

##### Principle: 
Go through each layer of NN, for each layer, drop a coin, so each layer has a 0.5 chance of keeping each node and 0.5 chance of removing each node, then we decide to remove the node.   

##### Implementation 
Most common: Inverted Dropout
- Illustrate with layer l = 3
- keep-prob = 0.8  The probability that a given hidden unit will be kept       
    ```
    d3 = np.random.rand(a3.shape[0], a3.shape[1]) < keep-prob
    a3 = np.multiply(a3, d3)        # a3 *= d3  
    a3 /= keep-prob      # invert dropout, this makes test time easier, because you have less of a scaling problem    
    ```
d3 generate a random matric, will be a boolean array where value is true and false(1, 0)
- Making predictions at test time, not use dropout at test time![](/assets/Screen Shot 2018-03-04 at 21.10.51.png)
    
    
### 1.7 Understanding Dropout

##### Why does drop-out work
- Dropout randomly knocks out units in NN
- Intuition: 
    - Can't rely on any one feature, so have spread out weights, so on every iteration, the network become smaller, so using a smaller neural network seems like it should have a regularizing effect
    - L2 penalty on different weights are different depending on the sice of the activations being multiplied that way 
    - It's possible to show that dropout has a similar effect to L2 regularization 
    - It's feasible to vary keep-prob by layer 
    - Debugging J function, just make keep-prob = 1
    ![](/assets/Screen Shot 2018-03-04 at 21.11.03.png)

### 1.8 Other regularization methods
##### Data augmentation 
- Getting more training data can help reduce over fitting, but can be expensive. 
So you could use below method to augment your data set and make additional fake training examples.
    - By flipping the images horizontally
    - Double the size of your training data 
    - Crop part of the image: zoom randomly of the image, then take random distortions and translations of the image 

- Early Stooping 
    - The NN was doing best around that iteration, so we just want to stop on your neural network halfway , and take whatever value achieved this dev set error
    - Why does this work? When you've haven't run many iterations for your NN yet, the parameters w will be close to 0, because with random initialization, you probably initialize w to small random values, as you iterate, as you train, w will get bigger and bigger until you have much large w, and early stopping means stopping the training of your neural network earlier 
    - **Downside**, ml process comprising several different steps, **early stopping couples the below two steps**, and you no longer can work on these two problems independently , because by stopping gradient descent early, you're sort of breaking what ever you're doing to optimize cost function J, because now you're not doing a great job reducing the cost function J. Instead of using 2 tools to solve two problems, early stopping use one tool to solve 2 problems.
        1. An algorithm to optimize the cost function j, just find w and b and make J(w, b) as small as possible 
            - Gradient Descent 
            - Momentum 
            - RMSprop
            - Adam 
        2. Not overfit, reduce variance 
            - Regularization 
            - Get more data   
            - Orthogonalization 
    - **Advantage**, running the gradient descent process just once, you could find values of small w, mid-size w, and large w, without needing to try a lot of values of the L2 regularization hyperparameter lambda 
    
    
    
### 1.9 Normalizing Input 

##### Normalizing training sets 
Corresponds two steps:
1. Subtract out or zero out the mean  
$$
x:= x-mean
$$
2. Normalize variance 
$$
x /= sigma ** 2
$$

##### Why normalize inputs 
![](/assets/Screen Shot 2018-03-04 at 22.34.59.png)
- Make your data more symmetric
     - If you don't normalize, you should set a small learning rate, the gradient descent might need a lot of steps to oscillate back and forth before finally finds its way to minimum, 
     - After normalization, you will have a more spherical contours, then whenever you start, gradient descent can pretty much go straight to the minimum
- Normalization guaranteed that all the features on a similar scale, will usually help your learning algorithm run faster 



### 1.10 Vanishing/exploding gradient 
> When training your deep network, the derivative or slopes can sometimes get wither very very big or very very small, maybe even exponentially small, and this makes training difficult 

![](/assets/Screen Shot 2018-03-04 at 22.57.15.png)

Partial Solution: Random weight initialization 

- At the weight W, if it's bigger than 1 or identity matric,then with a vary deep network, the activations can explode, and if W is just a little smaller than identity, the activation will decrease exponentially 
- With layer > 150, if the activation or gradients increase or decrease exponentially as a function of L, then these values could get really big or really small , and this makes training difficult, and it will take long time to make NN learn anything. 





        
         
        
        

        
            

