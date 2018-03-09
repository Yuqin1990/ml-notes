### 2.8 Adam Optimization Algorithm
Adam: Adaptive moment estimation
Put RMSprop and momentum together

![](/assets/Screen Shot 2018-03-09 at 11.55.32 PM.png)
![](/assets/Screen Shot 2018-03-09 at 11.55.43 PM.png)

### 2.9 Learning rate decay

- Gradient descent step is noisy 
- The line is into minimum.
- Learning rate should be smaller when close to minimum
![](/assets/Screen Shot 2018-03-10 at 12.15.36 AM.png)

##### How to decrease learning rate alpha
1 epoch = 1 pass through dot 

![](/assets/Screen Shot 2018-03-10 at 12.15.44 AM.png)

- manual decay, decrease learning rate hour by hour, day by day 


### 2.10 The problem of local optima 
In high dimension area, saddle point of a horse, that directive is 0
![](/assets/Screen Shot 2018-03-10 at 12.28.23 AM.png)


Problem of plateaus
- Unlikely to get stuck in a bad local optima as long as your training rate is larger than your NN, and the cost function J is defined in a relative high space
- Plateaus can make learning slow, this is where optimization algorithm can help the learning rate  









