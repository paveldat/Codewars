# Create Phone Number
Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.
# Example
```
create_phone_number([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]) # => returns "(123) 456-7890"
```
The returned format must be correct in order to complete this challenge.
Don't forget the space after the closing parentheses!
# Solution 1
```
#include <string>

std::string createPhoneNumber(const int arr [10]){
  int arr1[10];
  for (int i=0;i<10;i++)
    arr1[i] = arr[i];
  std::string str;
    for (int i: arr1) {
        str += std::to_string(i);
    }
  return "("+str.substr(0,3)+") "+str.substr(3,3)+"-"+str.substr(6);
}
```
