# Even or Odd
Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.
# Solution
```
std::string even_or_odd(int number) 
{
  return (number%2==0)? "Even":"Odd";
}
```