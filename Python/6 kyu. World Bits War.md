# World Bits War
Variation of this nice kata, the war has expanded and become dirtier and meaner; both even and odd numbers will fight with their pointy 1s. And negative integers are coming into play as well, with, ça va sans dire, a negative contribution (think of them as spies or saboteurs).

A number's strength is determined by the number of set bits (1s) in its binary representation. Negative integers work against their own side so their strength is negative. For example -5 = -101 has strength -2 and +5 = +101 has strength +2.

The side with the largest cumulated strength wins.

Again, three possible outcomes: odds win, evens win and tie.

# Examples:
```
bits_war([1,5,12]) => "odds win" #1+101 vs 1100, 3 vs 2
bits_war([7,-3,20]) => "evens win" #111-11 vs 10100, 3-2 vs 2
bits_war([7,-3,-2,6]) => "tie" #111-11 vs -1+110, 3-2 vs -1+2
```
# Solution 1
```
def bits_war(numbers):
    sum_even, sum_odd = 0,0
    for i in numbers:
        if i<0:
            if i%2!=0:
                a = bin(i)
                a = a[3:]
                b = a.count("1")
                sum_odd -= b
            elif i%2==0:
                a = bin(i)
                a = a[3:]
                b = a.count("1")
                sum_even -= b
        else:
            if i%2!=0:
                a = bin(i)
                a = a[2:]
                b = a.count("1")
                sum_odd += b
            elif i%2==0:
                a = bin(i)
                a = a[2:]
                b = a.count("1")
                sum_even += b
    if sum_even>sum_odd:
        return "evens win"
    elif sum_odd>sum_even:
        return "odds win"
    else:
        return "tie"
```
# Solution 2
```
def bits_war(numbers):
    odd, even = 0, 0
    for number in numbers:
        if number % 2 == 0:
            if number > 0:
                even += bin(number).count('1')
            else:
                even -= bin(number).count('1')
        else:
            if number > 0:
                odd += bin(number).count('1')
            else:
                odd -= bin(number).count('1')
    return 'odds win' if odd > even else 'evens win' if even > odd else 'tie'
```