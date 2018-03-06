### 2.1 Mini-batch gradient descent
##### Batch vs mini-batch gradient descent

Vectorization allows you to efficiently compute on m example
what if m = 5,000,000

mini-batches of 1,000 each
 
![](/assets/Screen Shot 2018-03-06 at 11.03.10 PM.png)

![](/assets/Screen Shot 2018-03-06 at 11.03.22 PM.png)

### 2.2 Understanding mini-batch gradient descent

![](/assets/Screen Shot 2018-03-06 at 11.12.05 PM.png)
#### Choosing your mini-batch size 

![](/assets/Screen Shot 2018-03-06 at 11.22.40 PM.png)
Optimize Cost function, it will always hit to the minimum, 
if size = m:  Batch gradient descent
if size = 1 stochastic gradient descent 

in practice: somewhere in-between i and m
Batch gradient descend(mini-batch size = m), too long per iteration 

 - In-between minibatch size not too big(small), future learning: 
 vectorization (~1000)
 - make progress without processing entire training set. 
 
 ##### Conclusion 
 - if small training set: use batch gradient(m < 2000)
 - Typical mini-batch size: 64, 128, 256, 512
 - Make sure mini-batch fit in CPU/GPU memory 

### 2.3 Exponentially weighted averages
Example: Temperature in London 
![](/assets/Screen Shot 2018-03-06 at 11.36.31 PM.png)
![](/assets/Screen Shot 2018-03-06 at 11.36.42 PM.png)
   