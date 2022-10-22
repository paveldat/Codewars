# IP Validation
Write an algorithm that will identify valid IPv4 addresses in dot-decimal format. IPs should be considered valid if they consist of four octets, with values between 0 and 255, inclusive.

Valid inputs examples:

## Examples of valid inputs:
```
1.2.3.4
123.45.67.89
```
## Invalid input examples:
```
1.2.3
1.2.3.4.5
123.456.78.90
123.045.067.089
```
## Notes:
* Leading zeros (e.g. `01.02.03.04`) are considered invalid
* Inputs are guaranteed to be a single string


# Solution 1
```
def is_valid_IP(strng):
    return strng.count('.') == 3 and all(octet.isdigit() and 0 <= int(octet) <= 255 and str(int(octet)) == octet for octet in strng.split('.'))
```
# Solution 2
```
def is_valid_IP(strng):)
    try:
        ip = strng.split('.')
        if len(ip) != 4:
            return False
        for octet in ip:
            if isinstance(int(octet), int):
                if len(octet) > 1 and octet[0] == '0' or int(octet) < 0 or int(octet) > 255 or ' ' in octet or '\n' in octet:
                    return False
        return True        
    except:
        return False
```