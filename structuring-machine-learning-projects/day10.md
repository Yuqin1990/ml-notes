# End to end deep leaning 

#### 2.9 What is end-to-end deep learning 
Speech recognition example

x: audio 
y: transcript

x ----MFCC-----> low level features ----ML----> phonemes(basic unit of sound) -------> words -------> y (transcript)

**E2E** 
audio ----------> transcript

You need large data set to make end-to-end approach work better than normal procedure

Face recognition:
use face recognition to replace RFID card 

1. Use a software to detect human face 
2. Zoom in that part, crop that part 
3. Then feed the image in NN

In this example, why 2-steps approach works better, 2 reasons:
1. Each of the two problems you're solving is much simpler
2. You have a lot of data for each of the 2 subtasks

But if you want e2e approach, you don't have much data for x(camera taken photo) to y(identity).

##### More examples
Machine translation 

English -> text -> ........-> French 

e2e
x(english) -> y(french)
**In reality, we do have a lot data for english -> french translations, e2e deep learning works quite well for machine translation. **


Estimating child's age:
2 steps: Image ---separate bones----> bone ---compare avg bone length for each age with the captured bone---> age 
e2e: image ----> age 

In this example, 2 steps approach works better cause there isn't enough data to train this task in an e2e fashion. 


#### 2.10 Whether to use end-to-end learning
Pros and cons of E2E deep learning:

Pros:
- Let data speak  
    - x -> y
    - Sppech recognition, phoneme is created by human, human force NN to use this to recognize audio via phoneme, but if you let NN learn what it wants, it may perform better without phoneme, 
- Less hand-designing of components needed

Cons:
    - May need large amount of data 
    - Excludes potentially useful hand-designed components 
        - If you don't much data, hand-designed component allows you to inject manual knowledge into the algorithm
        
        
Apply e2e deep learning
Key question: Do you have sufficient data to learn a function of the complexity needed to may x to y?
    
---
##### Drive.ai --- Self driving car

Images -> cars/pedestrians --> route --> steering 

E2E: Image -> Steering 

In this example, E2E is less promising than multiple steps approach.










