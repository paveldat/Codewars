# Sum of Digits / Digital Root
Digital root is the recursive sum of all the digits in a number.

Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.

**Examples**
```
    16  -->  1 + 6 = 7
   942  -->  9 + 4 + 2 = 15  -->  1 + 5 = 6
132189  -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6
493193  -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2
```
# Solution 1
```
int digital_root(int n)
{
    int sum = 0;
    int res = 0;
  int res1 = 0;
    while (n!=0){
      sum += n%10;
      n/=10;
    }
    while (sum!=0){
        res += sum%10;
        sum/=10;
    }
    while (res!=0){
      res1 += res%10;
      res/=10;
    }
  return res1;
}
```
# Solution 2
```
int digital_root(int n)
{
    int sum = 0;
    while (n!=0){
      sum += n%10;
      n/=10;
    }
    return (sum<=9)? sum:digital_root(sum);
}
```