# Build Tower
Build Tower by the following given argument:
number of floors (integer and always greater than 0).

Tower block is represented as *
Python: return a list;

for example, a tower of 3 floors looks like below
```
[
  '  *  ', 
  ' *** ', 
  '*****'
]
```
and a tower of 6 floors looks like below
```
[
  '     *     ', 
  '    ***    ', 
  '   *****   ', 
  '  *******  ', 
  ' ********* ', 
  '***********'
]
```

# Solution
```
def tower_builder(n_floors):
    a = []
    for i in range(n_floors): 
        a.append(' ' * (n_floors - i-1) + '*' * (i + 1) + '*' * i+ ' ' * (n_floors-i-1))
    return a
```