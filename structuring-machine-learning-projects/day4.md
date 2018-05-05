##### 1.8 Comparing to human level performance 

2 reasons compare human with ml system:

    1. The ML algorithms are working much better and become much more feasible in a lot of application areas. 
    2. It turns out the workflow of designing and building machine learning system, the workflow is much more efficient when you're trying to do something that humans can also do
    

Bayes Optima Error: the very best theoretical function for mapping from x to y that can never be surpress

![](/assets/Screen Shot 2018-05-05 at 10.57.01 PM.png)

Why compare to human-level performance:
Humans are quite good at a lot of tasks, so long as ML is worse than humans, you can:
    
    1. Get labeled data from humans
    2. Gain insights from manual error analysis:
       Why did a person get this right?
    3. Better analysis of bias/variance
    
    
##### 1.9 Avoidable bias
|Class|error rate 1| error rate 2|avoidable bias for example 2|
|-|-|-|
|Human| 1% | 7.5% |0|
|Training| 8% | 8% | 0.5% |
|Dev error | 10% | 10% |2.5%|

Think human-level error as a estimate for Bayes error for Bayes optimal error 

Solution for error rate 1: Focus on reducing bias, make training set close to human-level error 

Solution for error rate 2: Focus on reducing variance, make training and dev set error rate close to each other 

##### 1.10 Understanding human-level performance 
**Human-level error as a proxy for Bayers error **

Medical images classification example: 

Suppose:

|class|error rate|
|-|-|
|Typical human| 3% error |
|Typical doctor| 1% error |
|Experienced Doctor| 0.7% error |
|Team of experienced doctors|0.5% error |

Then human-level error should be <= 0.5% error

Error analysis example
Human proxy for Bayers  0.5%

Training error 5%
Dev error      6% 

Variance: 1%     Bias: 4.5%
So focus on bias error 

Summary of bias/variance with human-level performance 

Human-level error (proxy for Bayes error)  
Training error                           
Dev error

Error between human-level and training is avoidable bias
Error between training and dev error is variance 

##### 1.11 Surpassing human-level performance 
Problem where ML significantly surpasses human-level performance 

- Online AD
- Product recommendation 
- Logistics (predicting transit time)
- Loan approvals
    
Common:
Learning from structural data 
Not natural perception problem which human is good at 
Lots of data 

another areas that overpass human:
- speech recognition system 
- Some computer vision, image processing 
- Some medical tasks
    - Reading ECGs or diagnosing skin cancer, or certain narrow radiology task 


##### 1.12 Comparing to human-level performance 

Getting a supervised learning algorithm to work well means fundamentally assuming you can do 2 things:

    1. Can fit the training set pretty well = achieve low avoidable variance  
    2. The training set performance generalized pretty well to the dev/test set


Reducing (avoidable) bias and variance 

Avoidable bias: Human Level <--> Training error
Variance: Training error < -- > Dev error

|Class| error | methods |
|-|-|-|
|Human Level|||
||Avoidable bias| 1. Train bigger model 2. Train longer/better optimization algorithms 3. NN architecture/hyperparameters search |
|Training Error|||
||Variance|1. More data 2. Regularization, L2 and Dropout and Data augmentation 3. hyperparameters |
|Dev Error||| 




