# Optimization Algorithms

### 2.6 Gradient descent with momentum
1. Gradient descent with momentum is faster than the standard gradient descent algorithm 
2. In one sentence, the basic idea is to compute an exponentially weighted average of your gradients, and then use that gradient to update your weights instead 
![](/assets/Screen Shot 2018-03-08 at 18.16.35.png)

As a example, as 
1. You're trying to optimize a cost function, which has contours like the image top
2. The red dot denotes the position of the minimum, maybe you start gradient descent from here
3. You take one iteration of gradient descent either batch descent or mini-batch descent
![](/assets/Screen Shot 2018-03-08 at 18.25.38.png)
4. Gradient descent will take a lot of steps, slowly oscillate toward the minimum, and this up and down oscillations slow down gradient descent and prevents you from using a much larger learning rate, (**In particular, if you were to use a much larger learning rate, you might end up overshooting and end up diverging like the purple line, so the need to prevent the oscillations form getting too big forces you to use a learning rate that's not too large**)

>Another view of this problem, on the vertical axis you want your learning to be a bit slower, because you don't want those oscillations, but on the horizontal axis, you want faster learning , because you want aggressively move from left to right toward that minimum(the red dot)

##### Implemente gradient descent with momentum 
- On each iteration, during iteration t, compute the usual derivative dw db on the current mini batch, you compute v\_dW to be Beta V\_dW plus 1 minus Beta dW, this is similar to when we're previously computing - a moving average of the derivatives for w you're getting, similarly comoute V_db
- Then you would update your weights W = W - alpha * V_dw, b = b -alpha* V_db, what this does is smooth out the steps of gradient descent 
- The oscillation in the vertical direction will tend to average out to something closer to 0, so in the vertical direction, where you want to slow things down, this will average out positive and negative numbers , so the average will close to 0, on the horizontal direction, all the derivatives are pointing to the right of the horizontal direction, so the average in the horizontal direction will still be pretty big, so that's why with this algorithm, with few iterations, 
- You will find that the gradient descent with momentum ends up eventually just taking steps that much smaller oscillations in the vertical direction, but are more directed to just moving quickly in the horizontal direction, this allows your algorithm take a more straightforward path or to damp out the oscillations in this path to minimum 

##### Implementation details

![](/assets/Screen Shot 2018-03-08 at 19.01.46.png)

##### Conclusion 
It works good for bowl shape function, a ball which rolls to the minimum(rolling down the hill)

- The derivatives works like an acceleration for the velocity
- Beta works like friction which prevent the ball from speeding up without limit 
- Rather than gradient descent, just taking every single step independently of all previous steps, the ball can roll downhill and gain momentum, it can accelerate down this bowl and therefore gain momentum 

### 2.7 RMSprop
##### On iteration t:
Compute dw, db on current mini-batch
The function is much sloped in b direction than in w direction, So db square will relatively large while dw square is relatively small

![](/assets/Screen Shot 2018-03-09 at 11.32.23 PM.png)











