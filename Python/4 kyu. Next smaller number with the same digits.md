# Next smaller number with the same digits
Write a function that takes a positive integer and returns the next smaller positive integer containing the same digits.

For example:
```
next_smaller(21) == 12
next_smaller(531) == 513
next_smaller(2071) == 2017
```
Return -1 (for Haskell: return Nothing, for Rust: return None), when there is no smaller number that contains the same digits. Also return -1 when the next smaller number with the same digits would require the leading digit to be zero.
```
next_smaller(9) == -1
next_smaller(135) == -1
next_smaller(1027) == -1  # 0721 is out since we don't write numbers with leading zeros
```
* some tests will include very large numbers.
* test data only employs positive integers.
# Solution
```
def swap(string, index1, index2):
    str = list(string)
    str[index1], str[index2] = str[index2], str[index1]
    str = sorted(str[:index1]) + str[index1:]
    return ''.join(str)

def next_smaller(n):
    number = str(n)
    if list(number)==sorted(number):
        return -1
    reverse_n = number[::-1]
    for i, digit in enumerate(reverse_n,0):
        if any(n for n in reverse_n[:i] if n<digit):
            _,j = max(((num,j) for j,num in enumerate(reverse_n[:i]) if int(num)<int(digit)), key= lambda x:(x[0],x[1]))
            swp_n = swap(reverse_n,i,j)
            if not swp_n.endswith('0'):
                return int(swp_n[::-1])
    return -1
```