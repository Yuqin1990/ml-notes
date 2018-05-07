##### 2.2 Cleaning up incorrectly labeled data 

Example 1:

Classifier for cat:

label 1 for cat 
label 0 for non-cat

Incorrect label: label non-cat as 1

Training set: If the error is reasonable random, just left the error alone.

**Deep learning algorithm are robust to random errors, less robust for system errors**

|Image|Dog|great cat|blurry|Incprrectly labeled|comments|
|-|-|-|-|-|-|
|1|X||||Pitball|
|2|||X|||
|3||X|X|||
|...||||||
|||||X|Labeler missed cat in background|
|||||X|cat pic, not real cat|
|% of total|8%|43%|61%|6%|||

-----------------------------
Example 2:
situation a:
Overall dev set error.............10%   
Errors due incorrect labels.......0.6% 
Error due to other causes.........9.4%

situation b:
Overall dev set error.............2%   
Errors due incorrect labels.......0.6% 
Error due to other causes.........1.4%

**Situation b is worthwhile to fix up the incorrect labels **


---------------------
Correcting incorrect dev/test set example

1. Apply same process to dev and test sets to make sure they continue to come from the same distribution
2. Consider examining examples your algorithm got right as well as ones it got wrong (hard to do and not always done)
3. Train and dev/test data may now come from slightly different distributions. (Only fix incorrect labels in dev/test set may helpful)

-----
Conclusion: 
1. In building practical systems, there is more manual error analysis and more human insight that go into the system, which may help the researchers. 
2. Check the error labeled manually, may help find out the priority things to do.








