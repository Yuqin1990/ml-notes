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


    
    
  