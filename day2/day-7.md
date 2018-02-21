#### 4.1 Deep L-layer Neural network

![](/assets/Screen Shot 2018-02-22 at 01.23.00.png)

![](/assets/Screen Shot 2018-02-22 at 01.23.06.png)

- logistic regression: one layer network
- L: # of layers 
- n: # of units in different layer 

#### 4.2 Forward Propagation In a Deep Network
![](/assets/Screen Shot 2018-02-21 at 20.44.34.png)

- In all layers, apply formula z = wx + b, a = g(z)
- At first layer, a = x

#### 4.3 Getting your matrix dimensions right
![](/assets/Screen Shot 2018-02-22 at 01.26.15.png)

![](/assets/Screen Shot 2018-02-22 at 01.26.26.png)

- dw and w should be same dimensoion
- db and b should be same dimension


#### 4.4 Why Deep Network Work Well
- Face recognition 
    - first layer: recognition edges, small areas
    - second layer: find different parts of a face
    - third layer: compose parts together, recognize face 
    
> Informally: There are functions you can compute with small L-layer deep neural network that shallower networks required exponentially more hidden units to compute

- Multiple layer network is more efficient that shallow network

#### 4.5 Building blocks of deep neural networks
![](/assets/Screen Shot 2018-02-22 at 00.17.48.png)

- Layer L
  - Forward prop: 
    - Input: a[l-1] 
    - Params: w[l], b[l]
    - Output: a[l]
    - Cache: Z[l]
  - Backward prop:
    - Output: da[l-1]
    - Input: da[l]
    - Params: w[l], b[l], dz[l]
    - dw[l], db[l]
$$
w[l] := w[l] - learning\_rate * dw[l]
$$
$$
b[l] := b[l] - learning\_rate * db[l]
$$

![](/assets/Screen Shot 2018-02-22 at 00.17.57.png)


#### 4.6 Forward and backward propagation 
- Forward prop:
![](/assets/Screen Shot 2018-02-22 at 00.43.49.png)

- Backward prop:
![](/assets/Screen Shot 2018-02-22 at 00.43.56.png)

![](/assets/Screen Shot 2018-02-22 at 00.43.12.png)



#### 4.7 Parameters and hyper parameters
- Parameters: W, b
- Hyper Parameters(Control w and b):   
  - Learning rate, 
  - \# of iterations, 
  - \# of hidden layers, 
  - \# of hidden units,   
  - Choice of activation functions
  
- Other hyper parameters: momentum, mini batch size, various form of regularization parameters...

![](/assets/Screen Shot 2018-02-22 at 01.09.01.png)

> Applied deep learning is a very empirical process

- Try different settings and see which one works best 
- One model can be applied to different situations 
- But for the single situation, settings may change over time


#### 4.8 Why do this have to do with the brain 

![](/assets/Screen Shot 2018-02-22 at 01.18.07.png)

- NN: Forward and Backward prop
- Activation function just like a single biology neurons 
  


