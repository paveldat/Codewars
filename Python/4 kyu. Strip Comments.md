# Strip Comments
Complete the solution so that it strips all text that follows any of a set of comment markers passed in. Any whitespace at the end of the line should also be stripped out.

# Example:

Given an input string of:
```
apples, pears # and bananas
grapes
bananas !apples
```
The output expected would be:
```
apples, pears
grapes
bananas
```
The code would be called like so:
```
result = solution("apples, pears # and bananas\ngrapes\nbananas !apples", ["#", "!"])
# result should == "apples, pears\ngrapes\nbananas"
```
# Solution
```
def solution(string,markers):
    string = string.split('\n')
    for i in range(len(string)):
        s = string[i]
        for marker in markers:
            index = s.find(marker)
            if index != -1:
                s = s[:index].rstrip()
        string[i] = s
    return '\n'.join(string)
```