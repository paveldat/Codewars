# Third Angle of a Triangle
You are given two interior angles (in degrees) of a triangle.
Write a function to return the 3rd.
Note: only positive integers will be tested.
https://en.wikipedia.org/wiki/Triangle
# Solution 1
```
a=$1
b=$2
let res=180-$a-$b
echo "$res"
```
# Solution 2
```
a=$1
b=$2
echo $((180-a-b))
```