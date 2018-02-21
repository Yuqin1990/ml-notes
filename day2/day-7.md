#### 4.1 Deep L-layer Neural network
- logistic regression: one layer network
- L: # of layers 
- n: # of units in different layer 

#### 4.2 Forward Propagation In a Deep Network
![](/assets/Screen Shot 2018-02-21 at 20.44.34.png)

- In all layers, apply formula z = wx + b, a = g(z)
- At first layer, a = x

#### 4.3 Getting your matrix dimensions right

- dw and w should be same dimensoion
- db and b should be same dimension


#### 4.4 Why Deep Network Work Well
- Face recognition 
    - first layer: recognition edges, small areas
    - second layer: find different parts of a face
    - third layer: compose parts together, recognize face 
    
> Informally: There are functions you can compute with small L-layer deep neural network that shallower networks required exponentially more hidden units to compute

- Multiple layer network is more efficient that shallow network