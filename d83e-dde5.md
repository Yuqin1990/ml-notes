##### 1.4 Satisficing and optimizing metrics
Example:

    1. Accuracy 
    2. Running time

cost = accuracy - O.5 * runningTime
 
maximize accuracy, running time <= 100ms 

Optimize Accuracy, Satisficing Running time 

**If you have N metrics, 1 to optimize, N - 1 to satisficing **

Another example: Wakewords / Trigger words to wake up voice device

Accuracy 
\# of fake positive 

Maximize accuracy 
while at most 1 false positive every 24 hours
    
    
##### 1.5 Train/dev/test distribution 
Example 1: Cat classification dev/test set 

>Regions:

>|dev set|test set|
|--|--|
|US, UK|China, India, Australia|

Example 2: loan estimation 
>use zip code to predict loan 
they use middle income zip codes as dev set
use low income zip code as test set 
the result is disappointting 

**Conclusion:
Choose a dev set and test set to reflect data you expect to get in future and consider important to do well on.**
Set the dev/test set from same distribution. 

##### 1.6 Size of dev and test sets 
###### 1.6.1 Percentage of each set
Old Era:
70% Train 
30% Test 

60% Train 
20% Dev
20% Test

Now:
Given you have 1 million data set 
98% Train 
1% Dev
1% Test
So in the modern times, we have more data, so have less than 20% for test/dev set is more reasonable.



###### 1.6.2 Size of test set
Set you test set to be big enough to give high confidence in the overall performance of your system

If you do not need high confidence in performance, you can only have 2 sets: dev and train. no test set. 

 




    
  