# Q1: Import numpy library


```python
import numpy as np
```

# Q2: Generate a sequence of 15 floats using linspace() function


```python
new_linspace=np.linspace(0,8,15)
print(new_linspace)
```

    [0.         0.57142857 1.14285714 1.71428571 2.28571429 2.85714286
     3.42857143 4.         4.57142857 5.14285714 5.71428571 6.28571429
     6.85714286 7.42857143 8.        ]
    

# Q3: Create a 3-D array in shape (2, 2, 3) containing the four arrays given below 
Note : the array's name is up to you.

|      |       |          |         |
|------| ----- | -------- | ------- |
|arr1 | 1.1    | 2.1       | 3.1        |
|arr2 | 4.1    | 5.1       | 6.1        |
|arr3 | 7.1    | 8.1       | 9.1        |
|arr4 | 10.1   | 11.1      | 12.1       |


```python
arr_3D=np.array([
[
    [1.1,2.1,3.1],
    [4.1,5.1,6.1]
],
[
    [7.1,8.1,9.1],
    [10.1,11.1,12.1]
]
    
                ])
print(arr_3D.shape)
print(arr_3D,arr_3D.ndim)
```

    (2, 2, 3)
    [[[ 1.1  2.1  3.1]
      [ 4.1  5.1  6.1]]
    
     [[ 7.1  8.1  9.1]
      [10.1 11.1 12.1]]] 3
    

# Q4: Print the following:
Note: use the same array from Q3.
- Array's type.
- Array's elements datatype.
- Array's shape.
- Array's size.
- Array's dimention.


```python
print(type(arr_3D)
,arr_3D.dtype
,arr_3D.shape
,arr_3D.size
,arr_3D.ndim)
```

    <class 'numpy.ndarray'> float64 (2, 2, 3) 12 3
    

# Q5:  Change the array dimention from 3-D to 4-D
Note: use the same array from Q3.
- Create a new array to hold the changes. 
- Print the new array's dimention and shape.


```python
arr_4D=arr_3D.reshape(1,4,3,1)
print(arr_4D,arr_4D.ndim)
```

    [[[[ 1.1]
       [ 2.1]
       [ 3.1]]
    
      [[ 4.1]
       [ 5.1]
       [ 6.1]]
    
      [[ 7.1]
       [ 8.1]
       [ 9.1]]
    
      [[10.1]
       [11.1]
       [12.1]]]] 4
    

# Q6: Change the array's elements datatype to integer  
Note: use the same array from Q5.

- Create a new array to hold the changes. 
- Print the new array.


```python
arr_Q6=arr_4D.copy()
print(arr_Q6,arr_Q6.ndim)

```

    [[[[ 1.1]
       [ 2.1]
       [ 3.1]]
    
      [[ 4.1]
       [ 5.1]
       [ 6.1]]
    
      [[ 7.1]
       [ 8.1]
       [ 9.1]]
    
      [[10.1]
       [11.1]
       [12.1]]]] 4
    

# Q7: Print all array's elements using for loop
Note: use the same array from Q6.

Hint: use nditer()


```python
for i in np.nditer(arr_Q6):
    print(i)
```

    1.1
    2.1
    3.1
    4.1
    5.1
    6.1
    7.1
    8.1
    9.1
    10.1
    11.1
    12.1
    

# Q8:  Print number 8 using array slicing
Note: use the same array from Q6.


```python
arr_Q6[0,2,1,0]

```




    8.1



# Q9: Print number 5 and number 6 using array slicing
Note: use the same array from Q6.


```python
print(arr_Q6[0,1,1,0],arr_Q6[0,1,2,0])
```

    5.1 6.1
    

# Q10: Search for number 8 using where()
Note: use the same array from Q6.

Note: where() is only used with small data.

*the output represents the path of the index that leads to number 8*


```python
np.where(arr_Q6==8)
```




    (array([], dtype=int64),
     array([], dtype=int64),
     array([], dtype=int64),
     array([], dtype=int64))



# Q11: Reshape the array as the following

    array([[[ 1, 2],
            [ 3,  4],
            [ 5,  6]],

           [[ 7,  8],
            [ 9, 10],
            [11, 12]]])
            
 Note: use the same array from Q6.


```python
arr_q11=arr_Q6.reshape(2,3,2)
print(arr_q11)
```

    [[[ 1.1  2.1]
      [ 3.1  4.1]
      [ 5.1  6.1]]
    
     [[ 7.1  8.1]
      [ 9.1 10.1]
      [11.1 12.1]]]
    

# Q12: Join the given arrays below 
    arr1 = np.array([['A', 'B'], ['E', 'F']])
    arr2 = np.array([['C', 'D'], ['G', 'H']])
## Q12.1: Join the arrays without specifying the axis 


```python
arr1 = np.array([['A', 'B'], ['E', 'F']])
arr2 = np.array([['C', 'D'], ['G', 'H']])
#print(arr1)
#print(arr2)
arr3=np.concatenate((arr1,arr2))
print(arr3)
```

    [['A' 'B']
     ['E' 'F']
     ['C' 'D']
     ['G' 'H']]
    

# Q12.2: Join the arrays along rows with axis = 1 


```python
print(np.hstack((arr1,arr2)))
```

    [['A' 'B' 'C' 'D']
     ['E' 'F' 'G' 'H']]
    

# Q13: Split the array into two arrays with axis = 1, each array should contain four arrays. 
Note: use the same array from Q12.1


```python
ar1= arr3[0:2, :].reshape(2,2,1)
print(ar1)
ar2=arr3[2:,:].reshape(2,2,1)
print(ar2)
```

    [[['A']
      ['B']]
    
     [['E']
      ['F']]]
    [[['C']
      ['D']]
    
     [['G']
      ['H']]]
    
