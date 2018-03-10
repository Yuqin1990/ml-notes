# Multi-class classification
### 3.8 Softmax regresison
- Binary classification: label 1 or 0 
- Multi-class classification: 

Softmax regression: A generalization of logistic regression that lets you make predictions one of multiple classes

##### Recognize cats, dogs, and baby chicks
C = # of classes = 4 (0, 1, 2, 3)
In this case, we're going to build a neural network where the output layer has 4 output units, so n which is the units of layer L is going to equal to 4, we want each node of the output tell us the possibility of that class

##### Softmax layer  
Softmax activation function:
```t = e^(z[L])``` a (4, 1) dimension 

Detail example
- If you compute z[L], and z[L] is a 4-dimensional vector, [5, 2, -1, 3], then use the element-wise exponentiation to compute the vector t, t = [148.4m 7.4, 0.4, 20.1], t_norm = 176.3, a[l] = t/176.3
- This algorithm takes the vector Z[L] and matched it to tour probabilities that sum to 1.
- Summarize these steps to an activation function
- The unusual thing about this particular activation function is that this activation function g, it takes us input a 4 by 1 vector and it output a 4 by 1 vector 
 
##### Softmax examples
NN without hidden layer

The coloring in the input base on which one of the three outputs have the highest probability, this is like a generalization of logistic regression with sort of linear decision boundaries, but with more than 2 classes, instead of binary classes
The decision boundary between the two classes is linear boundary. 

### 3.9 Softmax regresison

### 3.10 Softmax regresison


