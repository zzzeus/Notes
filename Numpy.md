# This is a note about usages of numpy

## Contents
1. [Create]()



### Create
```python
import numpy as np
np.zeros((2,2))
np.ones((2,2))
np.arange(10).reshape(2,5)
np.random.rand(1,5)# array([[0.14601783, 0.88487647, 0.75384959, 0.0549264 , 0.60707236]])
np.random.randint(low=1,high=5,size=5) #array([3, 3, 2, 3, 1])
```

### Read
```python
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
 ```
### change 
```python
a2=np.transpose(a1) # cahnge the order of axis


```
* splice or join two piece
```python
'''
# Horizontal combination
np.hstack((a,b))
# Vertical combination
np.vstack((a,b))
'''
#example
a=np.arange(9).reshape(3,3)
b=a+10

print(a)
print()
print(b)
print('Horizontal combination:')
# Horizontal combination
print(np.hstack((a,b)))
print('vertical combination:')
# Vertical combination
print(np.vstack((a,b)))
print()
print(np.dstack((a,b)))


nx, ny = (3, 2)
x = np.linspace(0, 1, nx)
y = np.linspace(0, 1, ny)
xv, yv = np.meshgrid(x, y)
xv
'''
array([[0. , 0.5, 1. ],
       [0. , 0.5, 1. ]])
'''
```