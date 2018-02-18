#### 2.16 Python Numpy

Code example:

```
import numpy as np
a = np.random.random(5)

print(a.shape)

print(a.T)

print(np.dot(a, a.T))

a = np.random(5, 1)
print(a)

print(a.T)

print(np.dot(a,a.T)
```

- a = np.random.randn(5)
a.shape = (5,)
"rank 1 array" 
**Note: Don't use**

- a = np.random.randn(5,1)
a.shape = (5,1)
Column vector

- a = np.random.randn(1,5)
a.shape(1,5)
Row Vector 

