##### 2.6 Mismatched training and dev/test data 

###### Addressing data mismatch

- Carry out manual error analysis to try to understand difference between training and dev/test sets 
    - e.g. Rearview camera, lot of dev set example are noisy and car noisy, hard to recognize street number 
- Make training data more similar, or collect more data similar to dev/test set 
    - e.g. simulate noisy car data, add more street number speech in training set 
    

###### Make training data more similar to test data: Artificial data synthesis

1. 
"The quick brown fox jumps over the lazy dog" + Car noise = Synthesized in-car audio

Quickly make a lot of data that can sounds like record in car


2. Car recognition, generate car images using computer graphics, 
**problem: algorithm maybe overfitting to the small set of synthesized data **

----
Caution: Do not synthesis data from a small data set to avoid overfitting 



##### 2.7 Learning from multiple tasks
###### Transfer learning 

Given that you have a trained NN on image recognition 
(x, y) -> x is a image, y is an object 

If you want to use this NN for radiology diagnosis

What you should do:
1. Delete the output layer, delete the weights feeding into the last output layer
2. Create a new set of randomly initialized weights just for the last layer
3. Have the last layer output to radiology diagnosis
4. Retrain the last layer weights on the new radiology dataset, if you have a lot of data, you can retrain all the params in the NN 

From (x_old, y_old) to (x_new, y_new)
x_old: image   ->  x_new: Radiology image
y_old: object  -> y_new: diagnose you want to predict 

Image recognition Training: pre-training 
Radiology data Training: Fine tuning

###### Why it works
Cause a lot of the low level features such as detecting edges, detecting curves, detecting positive objects, learning from the image recognition may help the learning algorithm do better in radiology diagnosis. 


###### Another example, speech recognition -> wake word recognition system 

Input: audio 
Output: wake word

The process is same as example 1:
1. remove output 
2. random initialize params on last layer, or add some new layers to existing NN. 
3. Set output as new y, and retrain the whole NN. 

##### Why we may need transfer learning 
We may have a lot of data in old NN system, while less data for the problem we are transferring to, lots of data means NN can learn lots of low level features in earlier layers in NN, this help the target system to skip these process with smaller dataset. 

So if you have more data in target dataset,** DO NOT USE TRANSFER LEARNING.**


























