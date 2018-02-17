#### 2.9 Logistic Regression Gradient Descent
![](/assets/Screen Shot 2018-02-17 at 22.17.25.png)
**Logistic Regression Computation Graph**

x, w, b  ->  z = w * x + b  ->  a = sigmoid(z)  -> Loss function L(a, y)


#### 2.10 Logistic Regression on m examples

![](/assets/Screen Shot 2018-02-17 at 22.18.09.png)

![](/assets/Screen Shot 2018-02-17 at 22.18.59.png)

- x1, x2 represent two features
- Weakness: two for loops
  - loop over m training examples
  - loop over all the features
  - vectorization to reduce for loop
   
#### 2.11 Vectorization 
>Vectorization is the art of getting rid of explicit for loops in the code

Jupter Notebook Code: 

```python
import numpy as np
a = np.array([1,2,3,4]) 
```

```python
import time
a = np.random.rand(1000000)
b = np.random.rand(1000000)

tic = time.time()
c = np.dot(a, b)
toc = time.time()

print('Vectorization version:' + str(1000*(toc-tic))+ 'ms')

c = 0
tic = time.time()
for i in range(1000000):
  c += a[i] * b[i]
toc = time.time()
print('For loop:' + str(1000*(toc-tic))+ 'ms')

```
Summary: Vectorization takes less time than for logistic regression computation 

>Notes: Scalable deep learning implementations are done on a GPU(Graph process unit), jupter notebook runs on CPU, both CPU and GPU has parallelization instructions(SIMD instructions), which stands for a single instruction multiple data, but GPU performs better on SIMD          
