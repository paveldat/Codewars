# Number of trailing zeros of N!
Write a program that will calculate the number of trailing zeros in a factorial of a given number.

N! = 1 * 2 * 3 * ... * N

Be careful 1000! has 2568 digits...

For more info, see: http://mathworld.wolfram.com/Factorial.html

# Examples
```
zeros(6) = 1
# 6! = 1 * 2 * 3 * 4 * 5 * 6 = 720 --> 1 trailing zero

zeros(12) = 2
# 12! = 479001600 --> 2 trailing zeros
```
Hint: You're not meant to calculate the factorial. Find another way to find the number of zeros.
# Solution
```
def zeros(n):
    sum = 0
    while n>0:
        n//=5
        sum+=n
    return sum
```