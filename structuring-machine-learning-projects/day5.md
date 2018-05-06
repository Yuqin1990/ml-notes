##### 2.1 Error Analysis 
Carrying out error analysis 

###### 2.1.1 Example:

Assume you have a cat classifier
90% accurancy 
10% error 
the error are mostly recognize dog pic as cat, so should you try to male cat classifier do better on dogs?

Error Analysis: 

- Get ~100 mislabeled dev ser example
- Count up hoe many are dogs 

suppose only **5%** are dogs, so even if you solve the dog problem, you only solve 5% error rate, this gives you a performance ceiling  

But if you find **50%** are dogs, then solving the dog error will reduce the error rate by 50%. 

**This manual process only takes 5 - 10 minutes, but it could help you make a better decision 
**


###### 2.1.2 Evaluate multiple ideas in parallel 

Ideas for cat detection:

- Fix pictures of dogs being recognized as cats
- Fix great cats (lions, pnthers, etc...) being misrecognized 
- Improve performance on blurry images 

|Image|Dog|great cat|blurry|comments|
|-|-|-|-|-|
|1|X|||Pitball|
|2|||X||
|3||X|X||
|...|||||
|% of total|8%|43%|61%||

This process help you make better priorization decisions, and understand how promising different approached are to work on

