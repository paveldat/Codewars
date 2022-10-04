# Sort rectangles and circles by area II

In this kata you will be given a sequence of the dimensions of rectangles ( sequence with width and length ) and circles ( radius - just a number ).
Your task is to return a new sequence of dimensions, sorted ascending by area.

For example,
```
seq = [ (4.23, 6.43), 1.23, 3.444, (1.342, 3.212) ] # [ rectangle, circle, circle, rectangle ]
sort_by_area(seq) => [ ( 1.342, 3.212 ), 1.23, ( 4.23, 6.43 ), 3.444 ]
```
# Solution 1
```
from math import pi

def get_seq(dim):
    if isinstance(dim, tuple):
        return dim[0] * dim[1]
    else:
        return pi * dim ** 2

def sort_by_area(seq):
    res = {}
    for i in seq:
        res[i] = get_seq(i)
    sorted_res = sorted(res, key=res.get)
    return sorted_res
```
# Solution 2
```
from math import pi
def sort_by_area(seq): 
    return sorted(seq, key=lambda x: x[0] * x[1] if isinstance(x, tuple) else x * x * pi)
```