##### 1.7 When to change dev/test sets and metrics 
Example: Cat dataset

- Metric: classification error
- Algorithm A: 3% error  porn images categorized as cat 
- Algorithm B: 5% error  no porn images 

Algorithm A is better than B, but user prefer B because it not letting through pornographic images 

Orthogonalization for cat pictures: anti-porn

We should take a machine learning problem and break it into distinct steps. 

1. How to define a metric to evaluate classifiers 
2. Worry separately about how to do well on this metric 


Another example:

Algorithm A: 3% error
Algorithm B: 5% error

Dev/test

Dev/train set: Training on high resolution images 
But user images are low resolution and less well framed, B performs better than A

**Overall guideline: your current metric and data you are evaluating on doesn't corresponding on what you actually care about, then change your metric and test/dev sets, to better capture what you need your algorithm to actually do well on.**






