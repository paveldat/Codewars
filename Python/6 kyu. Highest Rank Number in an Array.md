# Highest Rank Number in an Array
Complete the method which returns the number which is most frequent in the given input array. If there is a tie for most frequent number, return the largest number among them.

Note: no empty arrays will be given.

# Examples
```
[12, 10, 8, 12, 7, 6, 4, 10, 12]              -->  12
[12, 10, 8, 12, 7, 6, 4, 10, 12, 10]          -->  12
[12, 10, 8, 8, 3, 3, 3, 3, 2, 4, 10, 12, 10]  -->   3
```
# Solution 1
```
def highest_rank(arr):
    res = max(arr, key=arr.count)
    cnt = arr.count(res)
    for i in arr:
        if arr.count(i) == cnt and i != res:
            if i > res:
                res = i
    return res
```
# Solution 2
```
def highest_rank(arr):
    return max(sorted(arr)[::-1], key=arr.count)
```