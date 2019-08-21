## This is a note about usages of numpy



### Examples
```python
import numpy as np
############# create ###########

np.zeros((2,2))
np.ones((2,2))
np.arange(10).reshape(2,5)
np.random.rand(1,5)# array([[0.14601783, 0.88487647, 0.75384959, 0.0549264 , 0.60707236]])
np.random.randint(low=1,high=5,size=5) #array([3, 3, 2, 3, 1])

############## read #############

a1=np.random.rand(2,5,5)
a1[1,2:,2:]

a3=a1.copy() # copy

print(a1)
print(a1>0)
print(a1[a1>0])

'''
output:
[[0.81006468 0.88234139 0.7575286  0.12222619 0.35648496]
 [0.79893086 0.85105473 0.04046778 0.82719331 0.82018073]]
[[ True  True  True  True  True]
 [ True  True  True  True  True]]
[0.81006468 0.88234139 0.7575286  0.12222619 0.35648496 0.79893086
 0.85105473 0.04046778 0.82719331 0.82018073]
 '''
 
############## change #############
a2=np.transpose(a1) # cahnge the order of axis


```
