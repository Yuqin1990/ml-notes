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










