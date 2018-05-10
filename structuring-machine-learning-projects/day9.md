##### 2.8 Learning from multiple tasks 
Multi-task learning 

Example 1: Simplified autonomous driving example
Self driving car need to detect:

- Pedestrians
- cars 
- stop signs 
- traffic lights 
...

1 image can have multiple(4) labels, building a single NN, looking at each image and solving 4 problems at same time. 

1 NN that resolve 4 problems performs better than 4 NN that solve 1 problem separately. 

---
When multi-task learning makes sense 
- Training on a set of tasks that could benefit from having shared lower-level features 
    - recognizing pedestrians, cars, stop signs 
- Usually: Amount of data you have for each task is quite similar. 
- Can train a big enough neural network to do well on all the tasks 


In practice, multi-task learning is used much less often than transfer learning, if you have a small data set, use transfer learning, while if you have a big dataset, and each feature has similar amount of data, just use multi-task learning.

