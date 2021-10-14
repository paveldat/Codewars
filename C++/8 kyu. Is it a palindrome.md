# Is it a palindrome?
Write a function that checks if a given string (case insensitive) is a palindrome.
# Solution
```
#include <string>
#include <iostream>
#include <algorithm>
std::string str_tolower(std::string s) {
    std::transform(s.begin(), s.end(), s.begin(), 
    [](unsigned char c){ return std::tolower(c); } 
    );
    return s;
}

bool isPalindrom (const std::string& str)
{
    std::string str1 = str;
    std::string str2 = str;
    std::reverse(str1.begin(), str1.end());
    return (str_tolower(str1)==str_tolower(str2));
}
```