# int32 to IPv4
Take the following IPv4 address: 128.32.10.1

This address has 4 octets where each octet is a single byte (or 8 bits).

1st octet 128 has the binary representation: 10000000
2nd octet 32 has the binary representation: 00100000
3rd octet 10 has the binary representation: 00001010
4th octet 1 has the binary representation: 00000001
So 128.32.10.1 == 10000000.00100000.00001010.00000001

Because the above IP address has 32 bits, we can represent it as the unsigned 32 bit number: 2149583361

Complete the function that takes an unsigned 32 bit number and returns a string representation of its IPv4 address.

# Examples
```
2149583361 ==> "128.32.10.1"
32         ==> "0.0.0.32"
0          ==> "0.0.0.0"
```
# Solution 1
```
def int32_to_ip(int32):
    res = bin(int32)
    res = res[2:]
    if res == "0":
        return "0.0.0.0"
    else:
        n = len(res)-24
        return str(int(res[:n],2))+"."+str(int(res[n:n+8],2))+"."+str(int(res[n+8:n+16],2))+"."+str(int(res[n+16:],2))
         
```
# Solution 2
```
from ipaddress import IPv4Address
def int32_to_ip(int32):
    return str(IPv4Address(int32))
```