#### 2.3 Build your first system quickly, then iterate

Speech recognition example

- Noisy background
    - cafe noise
    - car noise
- Accented speech 
- Far from microphone 
- Young children's speech 
- Stuttering (ah, uh, um)
- ... 

What you should do to quickly build a ML system:
- Set up dev/test set and metric 
- Build initial system quickly (maybe a quick & dirty implementation)
- Use bias/variance analysis to prioritize next step


#### 2.4 Mismatched training and dev/test data 
Training and testing on different distributions 


##### 2.4.1 Cat app example

|datasource|number|comment|
|-|-|-|-|
|Data from webpage|200,000|high resolution, large amount|
|Data from mobile app|10,000|blurry, low amount|


Solutions:

Dev set is aimed at target. the target of this system is to recognize cat from mobile taken photos

|Option|Advantage|Disadvantage|Comment|
|-|-|-|-|
|Put them together, randomly shuffle them into a train, dev, and test set|dev/test/train sets from same distribution|you may spend much time on optimize system to recognize cat from webpage image|not recommended|
|training set: 20,000 from web, dev/test: 10,000 all images from mobile|dev set is aiming target|Training distribution is different from dev/test|**recommended**|

##### 2.4.2 Speech recognition example
Build a speech activated rearview mirror for a car

|Training|Dev/test|
|-|-|
|purchased data, Smart speaker control, Voice keyboard| Speech activated rearview mirror|


-----
**Conclusion: Always use the aimed target data as dev/test set**


#### 2.5 Mismatched training and dev/test data 
Bias and Variance with mismatched data distributions 

##### 2.5.1 Cat classifier example

Assume human get almost 0% error (Bayers error)

Error analysis:
Training error    1%
Dev error         10%

It only reflects that dev set contains image that are much more different to classify accurately.

Two things changed when change from train set to dev set
1. The trained system never saw dev set data before
2. Train and dev/test sets from different distributions

Training-dev set: Same distribution as training set, but not used for training 

|Training error|Training-dev set|Dev error|problem|
|-|-|-|-|
|1%|9%|10%|variance problem|
|1%|1.5%|10%|data mismatch|
|10%|11%|12%|bias, cause human error is 0%|
|10%|11%|20%|2 issues: bias, data mismatch|

----
General principles: 
Bias/variance on mismatched training and dev/test sets

Human/bayers error  < -- avoidable bias -- >   Train error
Train error       < -- variance --- >  Train-dev error  
Train-dev error  < -- data mismatch - > Dev/test error  
Test error < -- degree of overfitting - > Dev/test error  

Dev/test set should from same distribution 


##### 2.5.2 More general formulation 
 Speech rearview mirror

||General speech recognition|Rearview mirror specific speech data|
|-|-|-|
|Human Level|"Human level" 4%|6% ask human to label|
|Error on examples trained on|"Training error" 7%|6% train specific data|
|Error on examples not trained on|"Training-dev set error" 10%|Dev/Test error 6%|

-----
**Conclusion: 
Use different data distribution for train/test/dev sets, this gives you more data to improve the performance of the algorithm, but also brings a new issue, the data mismatch.(difference between training-dev set error and dev/test set error)**





























