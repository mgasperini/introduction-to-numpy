|Python List | NumPy Array |
| :--------: | :---------: |
| Can contain data of different data types | Can contain data of same data type only |
| Takes a huge amount of time and memory for numerical computations of large data | Very cheap in terms of time and memory for numerical computations of large data |

### Compare Python List & Numpy Array

* Create two lists:  

```
# Create two python List say 'List_x' and 'List_your'
X_list = list(range(100000))
Y_list = list(range(100000))
```




* Import NumPy and Create two numpy arrays using the two Python lists:  

```
# Import numpy Library
import numpy as np
# Create two numpy array (say 'X' end 'Y') using above two list
X = np.array(X_list)
Y = np.array(Y_list)
```


* Define a function that will perform element-wise addition of two Python lists.  



```
# Define a function to calculate sum
# using python Lists X_list, Y_list)
def pure_python_version():
    Z = []
    for i in range(len(X_list)):
        Z.append(X_list[i] + Y_list[i])
```



* Define a function that will perform element-wise addition of two NumPy arrays.  


```
# Define a function to calculate sum
# using numpy arrays (X, Y)
def numpy_version():
# In numpy we can directly perform
# sum element-wise as
    Z = X + Y 
```





* Notice the time taken by both the functions (i.e. list_sum() and numpy\_arr\_sum()) to perform the same task.  


```
# Import Timer class from timeit Library
from timeit import Timer
```

```
timer_obj1 = Timer("pure_python_version()", 
                   "from __main__ import pure_python_version")
timer_obj2 = Timer("numpy_version()", 
                   "from __main__ import numpy_version")

print("Pure python version:",timer_obj1.timeit(1000))
print("Numpy version:",timer_obj2.timeit(1000))
```

**Output:**

```
Pure python version: 18.138080474000162
Numpy version: 0.16344507999929192
```


* You can observe here that the time taken by the python list to do the element-wise sum is much more than the NumPy arrays.