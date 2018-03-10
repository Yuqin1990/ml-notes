# Batch normalization 
### 3.6 Why does Batch Norm work
Reason:
1. Normalizing the input features, the X to mean 0 and variance 1
to take on a similar range of values that can speed up learning 
2. 

##### Learning on shifting input distribution 
Covariate shift: Given x -> y mapping, if the distribution of x changes, then you might retrain your learning algorithm, even the mapping function is unchanged. 

##### Why covariate shift is a problem with NN
The layer N get value a\_(n-1) from layer N-1, if w, b of layer N-1 changed, the a\_(n-1) changes, so the Layer N suffering from the problem of covariate shift
- ** The batch norm reduce the amount that the distribution of these hidden unit values shift around**
- The z will still change, but batch norm enables that the mean and variance of z will remain the same. 
- Batch norm reduces the problem of the input values changing. cause these values to be more stable. 
- Weaken and decouple the earlier layer params and later layers params 


##### Batch Norm as regularization 
- Each mini-batch is scaled by the mean/variance computed on just that mini-batch
- This adds some noise to the values z[l] within that minibatch. So similar to dropout, it adds some noise to each hidden layer's activations
- This has a slight regularization effect

### 3.7 Batch Norm at test time
Batch norm processes your data on mini batch at a time, but the test time you might need to process the examples one at a time.

##### Batch Norm at test time
??































