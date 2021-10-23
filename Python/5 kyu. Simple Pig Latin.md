# Simple Pig Latin
Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

# Examples
```
pig_it('Pig latin is cool') # igPay atinlay siay oolcay
pig_it('Hello world !')     # elloHay orldway !
```
# Solution
```
def pig_it(text):
    a,res = text.split(),[]
    for i in a:
        if i.isalpha():
            b = i[1:]+i[0]+'ay'
            res.append(b)
        else:
            res.append(i)
    return ' '.join(res)
```