# Vanilla Python
## Basic Info
- `C:\Users\Your Name>python --version`
- This is for determining which version of python is installed on your device
 - Running a Python file:
     - `C:\Users\Your Name>python helloworld.py`
     - Simply typing in python into your command prompt opens up the python command line, where you can actually write python code
```
C:\Users\Your Name>python
Python 3.6.4 (v3.6.4:d48eceb, Dec 19 2017, 06:04:45) [MSC v.1900 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> print("Hello, World!")
Hello, World!
```
 - To get out of the python command line: `exit()`
## Syntax
 - Indentations in python just indicate a code block
     - Ideally, it’s 4 spaces worth, this is a good practice
    - This should be kept uniform, or python will give you errors with comments
 - `#This is a comment`
 - Can be placed at the end of a line of code, or on their own line
 - Multiline strings can also be used to create comments
```
"""
This is a comment
written in
more than just one line
"""
print("Hello, World!")
```
## Variables
 - Created by just assigning a name and a value
     - `X = 17`
 - Types can be changed even after the variable has been defined earlier, by just redefining it with a different type
```
X = 17
X = ‘stupid’
print(x)
```
 - You can also cast variables
```
x = str(3)    # x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0
```
 - To get the type of a variable: `type()`
```
x = 5
y = "John"
print(type(x))
print(type(y))
```
 - Variables are case sensitive
 - Variable name rules
     - Must start with a letter or an underscore, cannot start with a number
     - Can only contain alphanumeric characters as well as the underscore
     - Cannot be any of the python keywords
```
#Legal Variable Names
myvar = "John"
my_var = "John"
_my_var = "John"
myVar = "John"
MYVAR = "John"
myvar2 = "John"
#Illegal Variable Names
2myvar = "John"
my-var = "John"
my var = "John"
```
 - Multiple variable assignments can be done on one line
```
#Many values to multiple variables
x, y, z = "Orange", "Banana", "Cherry"
print(x)
print(y)
print(z)
#One value to many variables
x = y = z = "Orange"
print(x)
print(y)
print(z)
#Unpacking a collection
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)
print(y)
print(z)
```
 - To print out multiple values, just go print(x, y, z)
 - Alternatively you can just use the `+` operator
     - For numerical data types, this would just print out the sum
 - `+` operator would not work if the variables had different data types, such as a string and an integer
 - Variables defined outside of any function are global by default, but if you want to define a global variable from inside of a function, you just use the global keyword
     - If you want to change the value of a global variable inside of a function, you also need to use the global keyword
```
x = "awesome"
def myfunc():
  global x
  x = "fantastic"
myfunc()
print("Python is " + x)
```
## Data Types
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
## Python Casting
 - You can specify variable type in the declaration as well
```
x = int(1)   # x will be 1
y = int(2.8) # y will be 2
z = int("3") # z will be 3

x = float(1)     # x will be 1.0
y = float(2.8)   # y will be 2.8
z = float("3")   # z will be 3.0
w = float("4.2") # w will be 4.2

x = str("s1") # x will be 's1'
y = str(2)    # y will be '2'
z = str(3.0)  # z will be '3.0'

#int() - constructs an integer number from an integer literal, a float literal (by removing all decimals), or a string literal (providing the string represents a whole number)

#float() - constructs a float number from an integer literal, a float literal or a string literal (providing the string represents a float or an integer)

#str() - constructs a string from a wide variety of data types, including strings, integer literals and float literals
```
## Python Strings
 - use either single or double quotes to mark a string
     - Display using print()
 - if you want to use quotes inside of a string, they need to be surrounded with either single or double quotes, whichever one doesn’t match the ones encompassing the whole string
```
print("It's alright")
print("He is called 'Johnny'")
print('He is called "Johnny"')
```
 - you can also use triple quotes for multiline strings, either 3 single quotes, or 3 double quotes
 - Strings are basically arrays, so you can print out their indexes as well
```
a = "Hello, World!"
    print(a[1])

for x in "banana":
    print(x)

a = "Hello, World!"
print(len(a))

txt = "The best things in life are free!"
print("free" in txt)

txt = "The best things in life are free!"
if "free" in txt:
    print("Yes, 'free' is present.")

txt = "The best things in life are free!"
print("expensive" not in txt)

txt = "The best things in life are free!"
if "expensive" not in txt:
    print("No, 'expensive' is NOT present.")
```
### Slicing Strings
```
b = "Hello, World!"
print(b[2:5]) #5 not included
```
 - To slice from the start, just include the end character position
```
b = "Hello, World!"
print(b[:5])
```
 - You can also slice from some position all the way to the end
```
b = "Hello, World!"
print(b[2:])
```
 - You can use negative slicing to remove characters from the end
 - Get the characters: From: "o" in "World!" (position -5) To, but not included: "d" in "World!" (position -2):
    ```
    b = "Hello, World!"
    print(b[-5:-2])
    ```
### String modification & String concatenation
 - Upper case
```
a = "Hello, World!"
print(a.upper())

a = "Hello, World!"
print(a.lower())
```
 - removes whitespace
```
a = " Hello, World! "
print(a.strip()) # returns "Hello, World!" 

a = "Hello, World!"
print(a.replace("H", "J"))

a = "Hello, World!"
print(a.split(",")) # returns ['Hello', ' World!']

a = "Hello"
b = "World"
c = a + b
print(c)

a = "Hello"
b = "World"
c = a + " " + b
print(c)
```
### Formatted Strings & Escape Characters
#### Formatted Strings
```
age = 36
txt = f"My name is John, I am {age}"
print(txt)
```
 - you can also add modifiers to the formatted strings, using a colon and then some specifier
 - Display the price with 2 decimals:
```
price = 59
txt = f"The price is {price:.2f} dollars"
print(txt)
```
 - They can also contain python code
```
txt = f"The price is {20 * 59} dollars"
print(txt)
```
#### Escape Characters
 - used to insert illegal characters into a string
     - `txt = "We are the so-called \"Vikings\" from the north."`
```
\\ - Backslash
\' - Single quote
\" - Double quote
\n - Newline
\t - Horizontal tab
\r - Carriage return
\f - Form feed
\b - Backspace
\ooo - Octal value (e.g., \141 represents 'a')
\xhh - Hexadecimal value (e.g., \x61 represents 'a')
\N{name} - Unicode character by name (e.g., \N{LATIN SMALL LETTER A} represents 'a')
\uhhhh - Unicode character with a 16-bit hex value (e.g., \u00E9 represents 'é')
\Uhhhhhhhh - Unicode character with a 32-bit hex value (e.g., \U0001F600 represents 😀)
\v - Vertical tab
\a - ASCII bell (alert sound)
```
 - You can use raw strings to prevent these from being processed
```
print(r"Newline escape: \n")
Outputs: Newline escape: \n
```
### String Methods
#### Basic Information
```len("hello")  # Returns the length of the string: 5```

##### Case Conversion
```
"Hello".lower()          # Converts to lowercase: 'hello'
"Hello".upper()          # Converts to uppercase: 'HELLO'
"hello world".capitalize()  # Capitalizes the first character: 'Hello world'
"hello world".casefold() # Converts to lowercase (more aggressive): 'hello world'
"hello world".title()    # Capitalizes the first character of each word: 'Hello World'
"Hello".swapcase()       # Swaps the case of all characters: 'hELLO'
```
##### Alignment
```
"hello".center(10, '-')  # Centers the string: '--hello---'
"hello".ljust(10, '-')   # Left-aligns the string: 'hello-----'
"hello".rjust(10, '-')   # Right-aligns the string: '-----hello'
```
##### Trimming and Stripping
```
"  hello  ".strip()      # Removes leading and trailing characters: 'hello'
"  hello".lstrip()       # Removes leading characters: 'hello'
"hello  ".rstrip()       # Removes trailing characters: 'hello'
```
#### Search and Replace
```
"hello".find("l")        # Finds the first occurrence of 'l': 2
"hello".rfind("l")       # Finds the last occurrence of 'l': 3
"hello".index("l")       # Like find() but raises ValueError if not found: 2
"hello".rindex("l")      # Like rfind() but raises ValueError if not found: 3
"hello world".count("o") # Counts occurrences of 'o': 2
"hello world".replace("world", "Python")  # Replaces substrings: 'hello Python'
```
#### Splitting and Joining
```
"hello world".split()    # Splits into a list: ['hello', 'world']
"apple,banana,grape".split(',')  # Splits by delimiter: ['apple', 'banana', 'grape']
"hello\nworld".splitlines()  # Splits by line breaks: ['hello', 'world']
",".join(['apple', 'banana', 'grape'])  # Joins a list into a string: 'apple,banana,grape'
```
#### Checking String Content
```
"hello".startswith("he") # Checks if it starts with 'he': True
"hello".endswith("lo")   # Checks if it ends with 'lo': True
"hello".isalnum()        # Checks if all characters are alphanumeric: True
"hello".isalpha()        # Checks if all characters are in the alphabet: True
"12345".isdigit()        # Checks if all characters are digits: True
"hello123".isalnum()     # Checks if all characters are alphanumeric: True
"    ".isspace()         # Checks if all characters are whitespace: True
"Hello World".istitle()  # Checks if it's title-cased: True
"HELLO".isupper()        # Checks if all characters are uppercase: True
"hello".islower()        # Checks if all characters are lowercase: True
"12345".isdecimal()      # Checks if all characters are decimal numbers: True
"12345".isnumeric()      # Checks if all characters are numeric: True
"hello".isascii()        # Checks if all characters are ASCII: True
"my_var".isidentifier()  # Checks if it's a valid identifier: True
"hello".isprintable()    # Checks if all characters are printable: True
```
##### Formatting Strings
```
"Hello, {}".format("World")  # Formats specified values in a string: 'Hello, World'
"Name: {name}, Age: {age}".format(name="Alice", age=25)  # Named placeholders
"Price: {:.2f}".format(19.999)  # Formats a float to 2 decimal places: 'Price: 20.00'
"hello".zfill(10)            # Pads with zeroes: '000000hello'
```
##### Encoding and Decoding
```
"hello".encode("utf-8")      # Encodes the string to bytes: b'hello'
b'hello'.decode("utf-8")     # Decodes bytes back to a string: 'hello'
```
##### Translating and Mapping
```
"hello".translate("world")   # Returns a translated string (requires a translation table)
"hello".maketrans("aeiou", "12345")  # Creates a translation table
"hello".expandtabs(4)        # Sets tab size in the string: 'hello'
```
##### Partitioning and Splitting
```
"hello world".partition(" ") # Partitions the string: ('hello', ' ', 'world')
"hello world".rpartition(" ")# Partitions from the right: ('hello', ' ', 'world')
"apple,banana,grape".rsplit(",", 1)  # Splits at last occurrence of delimiter: ['apple,banana', 'grape']
```


















