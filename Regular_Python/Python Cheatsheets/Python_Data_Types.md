# Data Types
```
# Python Data Types Cheat Sheet

# 1. Numeric Types
a = 10          # int: Integer numbers
b = 3.14        # float: Floating-point numbers (decimals)
c = 1 + 2j      # complex: Complex numbers with real and imaginary parts

# 2. Sequence Types
s = "Hello"     # str: Strings (text)
lst = [1, 2, 3] # list: Ordered, mutable collection of items
tpl = (4, 5, 6) # tuple: Ordered, immutable collection of items
rng = range(5)  # range: Immutable sequence of numbers

# 3. Text Type
s = "Python"    # str: A sequence of Unicode characters

# 4. Set Types
st = {1, 2, 3}          # set: Unordered collection of unique items
fst = frozenset([4, 5]) # frozenset: Immutable set

# 5. Mapping Type
dct = {'key': 'value'}  # dict: Key-value pairs (unordered, mutable)

# 6. Boolean Type
flag = True             # bool: Represents True or False

# 7. Binary Types
b = b'hello'            # bytes: Immutable sequence of bytes
ba = bytearray([1, 2])  # bytearray: Mutable sequence of bytes
mv = memoryview(b)      # memoryview: A view of binary data without copying

# 8. None Type
n = None                # NoneType: Represents the absence of a value

# 9. Callable Types
def my_function():      # Functions and methods are callable objects
    return "Hello!"

# 10. Iterator Types
itr = iter([1, 2, 3])   # Iterator: An object returned by functions like iter()

# 11. Custom Types
class MyClass:          # User-defined classes
    pass
obj = MyClass()         # Instances of user-defined classes

# 12. Special Types (Optional Typing)
from typing import List, Tuple, Dict, Set, Union, Any, Optional

data: List[int] = [1, 2, 3]   # List of integers
pair: Tuple[int, str] = (1, "a")  # Tuple with specific types
mapping: Dict[str, int] = {"key": 42} # Dictionary with string keys and int values
unique: Set[str] = {"apple", "banana"}  # Set of strings
value: Union[int, str] = 42  # Variable that can be int or str
optional_value: Optional[int] = None  # Int or None
```
- You can use type() to get the type of any variable
