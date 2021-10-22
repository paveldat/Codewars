# Duplicate Encoder
The goal of this exercise is to convert a string to a new string where each character in the new string is "(" if that character appears 
only once in the original string, or ")" if that character appears more than once in the original string. Ignore capitalization when determining 
if a character is a duplicate.

# Examples
```
"din"      =>  "((("
"recede"   =>  "()()()"
"Success"  =>  ")())())"
"(( @"     =>  "))((" 
```
# Notes
Assertion messages may be unclear about what they display in some languages. If you read "...It Should encode XXX", the "XXX" is the expected result, not the input!
# Solution
```
#include <string>
#include <algorithm>
std::string str_tolower(std::string s) {
    std::transform(s.begin(), s.end(), s.begin(), 
    [](unsigned char c){ return std::tolower(c); } 
    );
    return s;
}
std::string duplicate_encoder(const std::string& word){
  std::string res = "";
  std::string word_new = str_tolower(word);
  for (auto i:word_new){
    if (std::count(word_new.begin(), word_new.end(), i) > 1)
      res+=")";
    else
      res+="(";  
  }
  return res;
}
```