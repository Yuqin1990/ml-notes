

##### 1.1 Why ML Strategy
Ideas for improving NN:
1. Collect more data
2. Collect more diverse training set
3. Train algorithm longer with gradient descent 
4. Try Adam instead of gradient descent 
5. Try bigger network
6. Try smaller network
7. Try dropout 
8. Add L2 regularization 
9. Network architecture
    - Activation functions 
    - \# hidden units 
    
**Objective of ML Strategy**: Teach a number of strategies that is, ways of analyzing a machine learning problem that will point you in the direction of the most promising things to try



##### 1.2 Orthogonalization 
Fit training set well on cost function 

Fit dev set well on cost function 

Fit test set well on cost function 

Performs well in real world 


Tips: Tune separately, you'd better not use early stopping, cause it affect 2 things at same time. 

##### 1.3 Setting up yout goal
Set up a single real number evaluation metric for your problem 

Not Recommended to use 2 metric precision and recall to pick a classifier, you just have to find a new evaluation metric that combines precision and recall

In this case, we can use F1 score, the F1 score is defined by the formula 
P represent precision, R represents Recall

F1 score = Harmonic mean of precision P and recall R


**Dev set + Single number evaluation metric will speed up iterating. **

























