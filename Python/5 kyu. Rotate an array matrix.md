# Rotate an array matrix
Write a rotate function that rotates a two-dimensional array (a matrix) either clockwise or anti-clockwise by 90 degrees, and returns the rotated array.

The function accepts two parameters: an array, and a string specifying the direction or rotation. The direction will be either `"clockwise"` or `"counter-clockwise"`.

Here is an example of how your function will be used:
```
matrix = [[1, 2, 3],
          [4, 5, 6],
          [7, 8, 9]]

rotate(matrix, "clockwise") #  Would return  [[7, 4, 1], [8, 5, 2],  [9, 6, 3]]
```
To help you visualize the rotated matrix, here it is formatted as a grid:
```
 [[7, 4, 1],
  [8, 5, 2],
  [9, 6, 3]]
```
Rotated counter-clockwise it would looks like this:
```
 [[3, 6, 9],
  [2, 5, 8],
  [1, 4, 7]]
```
# Solution 1
```
def rotate(matrix, direction): 
    def clockwise_rotate(matrix):
        for i in range(3):
            matrix = counter_clockwise_rotate(matrix)
        return matrix
    def counter_clockwise_rotate(matrix):
        matrix_tmp = [[0]*len(matrix) for _ in range(len(matrix[0]))]
        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                matrix_tmp[j][i] = matrix[i][j]
        return matrix_tmp[::-1]
    if direction == 'clockwise':
        return clockwise_rotate(matrix)
    elif direction == 'counter-clockwise':
        return counter_clockwise_rotate(matrix)
         
```
# Solution 2
```
import numpy as np
d = {"clockwise":3, "counter-clockwise":1}

def rotate(matrix, direction):
    return np.rot90(matrix, d[direction]).tolist()
         
```