# +1 Array
Given an array of integers of any length, return an array that has 1 added to the value represented by the array.
* the array can't be empty
* only non-negative, single digit integers are allowed
Return `nil` (or your language's equivalent) for invalid inputs.

## Examples
For example the array `[2, 3, 9]` equals `239`, adding one would return the array `[2, 4, 0]`.

`[4, 3, 2, 5]` would return `[4, 3, 2, 6]`

# Solution 1
```
def up_array(arr):
    try:
        for num in arr:
            if len(str(num)) > 1:
                return None
        return list(map(int,str((int(''.join(map(str, arr))) + 1))))
    except:
        return None
```
# Solution 2
```
def up_array(arr):
    return None if not arr or min(arr) < 0 or max(arr) > 9 else list(map(int,str((int(''.join(map(str, arr))) + 1))))
```