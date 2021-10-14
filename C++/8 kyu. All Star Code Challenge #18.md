# All Star Code Challenge #18
**This Kata is intended as a small challenge for my students**

All Star Code Challenge #18

Create a function that accepts 2 string arguments and returns an integer of the count of occurrences the 2nd argument is found in the first one.

If no occurrences can be found, a count of 0 should be returned.
```
("Hello", "o")  ==>  1
("Hello", "l")  ==>  2
("", "z")       ==>  0
```
**Notes**:

1. The first argument can be an empty string
2. The second string argument will always be of length 1
# Solution
```
#include <string>

unsigned int strCount(std::string word, char letter){
  int sum = 0;
  for (int i=0;i<word.length();i++){
    if (word[i]==letter)
      sum++;
  }
  return sum;
}
```