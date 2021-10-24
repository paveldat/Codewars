# Ninety Nine Thousand Nine Hundred Ninety Nine
Write a method that takes a number and returns a string of that number in English.

Your method should be able to handle any number between 0 and 99999. If the given number is outside of that range or not an integer, the method should return an empty string.

#Examples
```
0      -->  "zero"
27     -->  "twenty seven"
100    -->  "one hundred"
7012   -->  "seven thousand twelve"
99205  -->  "ninety nine thousand two hundred five"
```
# Solution
```
def number_to_english(n):
    d = { 0 : 'zero', 1 : 'one', 2 : 'two', 3 : 'three', 4 : 'four', 5 : 'five',
          6 : 'six', 7 : 'seven', 8 : 'eight', 9 : 'nine', 10 : 'ten',
          11 : 'eleven', 12 : 'twelve', 13 : 'thirteen', 14 : 'fourteen',
          15 : 'fifteen', 16 : 'sixteen', 17 : 'seventeen', 18 : 'eighteen',
          19 : 'nineteen', 20 : 'twenty',
          30 : 'thirty', 40 : 'forty', 50 : 'fifty', 60 : 'sixty',
          70 : 'seventy', 80 : 'eighty', 90 : 'ninety' }
    k = 1000
    m = k * 1000
    b = m * 1000
    
    if n<0 or int(n)!=n or n>=100000:
        return ''
    
    if (n < 20):
        return d[n]

    if (n < 100):
        if n % 10 == 0: return d[n]
        else: return d[n // 10 * 10] + ' ' + d[n % 10]

    if (n < k):
        if n % 100 == 0: return d[n // 100] + ' hundred'
        else: return d[n // 100] + ' hundred ' + number_to_english(n % 100)

    if (n < m):
        if n % k == 0: return number_to_english(n // k) + ' thousand'
        else: return number_to_english(n // k) + ' thousand ' + number_to_english(n % k)
```