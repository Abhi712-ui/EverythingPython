# Booleans
```
print(10 > 9)
print(10 == 9)
print(10 < 9)

a = 200
b = 33

if b > a:
    print("b is greater than a")
else:
    print("b is not greater than a")
```
- You can also evaulate variables as true or false, which can be done through the use of the `bool` function


```
print(bool("Hello"))
print(bool(15))
```
- All Strings except empty strings evaluate to `True`
- Any number is `True` except for 0
- All tuples, dicts, lists, and sets evaluate to `True`, as long as they are not empty
- For custom objects:
    - If the object implements the length method, and the length is 0, then the object will evaluate to false
