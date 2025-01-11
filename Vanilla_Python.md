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
## Booleans
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

## Python Operators
### 1. Arithmetic Operators
 - Used for mathematical operations.
```
+   # Addition: a + b
-   # Subtraction: a - b
*   # Multiplication: a * b
/   # Division: a / b
%   # Modulus (remainder): a % b
**  # Exponentiation (power): a ** b
//  # Floor division (integer division): a // b
```
### 2. Comparison (Relational) Operators
 - Used to compare values and return a Boolean result.
```
==  # Equal to: a == b
!=  # Not equal to: a != b
>   # Greater than: a > b
<   # Less than: a < b
>=  # Greater than or equal to: a >= b
<=  # Less than or equal to: a <= b
```

### 3. Assignment Operators
 - Used to assign values to variables.
```
=   # Assign: a = b
+=  # Add and assign: a += b (equivalent to a = a + b)
-=  # Subtract and assign: a -= b
*=  # Multiply and assign: a *= b
/=  # Divide and assign: a /= b
%=  # Modulus and assign: a %= b
//= # Floor divide and assign: a //= b
**= # Exponent and assign: a **= b
&=  # Bitwise AND and assign: a &= b
|=  # Bitwise OR and assign: a |= b
^=  # Bitwise XOR and assign: a ^= b
>>= # Bitwise right shift and assign: a >>= b
<<= # Bitwise left shift and assign: a <<= b
```

### 4. Logical Operators
 - Used to combine conditional statements.
```
and # Logical AND: a and b (True if both a and b are True)
or  # Logical OR: a or b (True if either a or b is True)
not # Logical NOT: not a (True if a is False)
```
### 5. Bitwise Operators
 - Operate on binary representations of integers.
```
&   # Bitwise AND: a & b
|   # Bitwise OR: a | b
^   # Bitwise XOR: a ^ b
~   # Bitwise NOT: ~a
<<  # Bitwise left shift: a << b
>>  # Bitwise right shift: a >> b
```

### 6. Membership Operators
 - Check for membership in sequences (like lists, strings, tuples).
```
in     # True if a value is in the sequence: a in b
not in # True if a value is not in the sequence: a not in b
```
### 7. Identity Operators
 - Check whether two variables refer to the same object in memory.
```
is     # True if a and b refer to the same object: a is b
is not # True if a and b do not refer to the same object: a is not b
```
### 8. Special Operators
 - Ternary (Conditional) Operator
 - Used for conditional expressions.
```
a if condition else b  # Returns a if condition is True, otherwise b
```
### Operator Precedence
 - Controls the order of operations in an expression. 
 - Parentheses `()` can be used to override precedence.

## Python Lists
 - `mylist = ["apple", "banana", "cherry"]`
 - used to store multiple values in python
 - one of four main data structures, which are lists, tuples, sets, and dicts
 - created using square brackets
 - ordered, meaning that new elements will always be added to the end of the list
 - lists are also changable and can contain duplicates
 - also uses `len`
 - can contain multiple different data types in one list

### List Methods in Python

#### 1. append()
 - Adds an element to the end of the list.
```
my_list = [1, 2, 3]
my_list.append(4)  # my_list becomes [1, 2, 3, 4]
```

### 2. extend()
 - Extends the list by appending elements from another iterable.
 - Can also take in another iterable to be added to the list
```
my_list = [1, 2, 3]
my_list.extend([4, 5])  # my_list becomes [1, 2, 3, 4, 5]
```
### 3. insert()
 - Inserts an element at a specified position.
```
my_list = [1, 2, 4]
my_list.insert(2, 3)  # my_list becomes [1, 2, 3, 4]
```
### 4. remove()
 - Removes the first occurrence of a specified value.
 - Alternatively, the del function could be used to remove a specific value from the list, taking in the index of the value
 - The del keyword can also delete the list completely
```
my_list = [1, 2, 3, 2]
my_list.remove(2)  # my_list becomes [1, 3, 2]
del thislist[0]
```
### 5. pop()
 - Removes and returns the element at a specified index (default is the last).
```
my_list = [1, 2, 3]
my_list.pop()     # Returns 3; my_list becomes [1, 2]
my_list.pop(0)    # Returns 1; my_list becomes [2]
```
### 6. clear()
 - Removes all elements from the list.
```
my_list = [1, 2, 3]
my_list.clear()   # my_list becomes []
```
### 7. index()
 - Returns the index of the first occurrence of a specified value.
```
my_list = [1, 2, 3, 2]
my_list.index(2)  # Returns 1
my_list.index(2, 2)  # Returns 3 (start search at index 2)
```
### 8. count()
 - Returns the number of occurrences of a specified value.
```
my_list = [1, 2, 3, 2]
my_list.count(2)  # Returns 2
```
### 9. sort()
 - Sorts the list in ascending order (by default).
```
my_list = [3, 1, 2]
my_list.sort()    # my_list becomes [1, 2, 3]
my_list.sort(reverse=True)  # my_list becomes [3, 2, 1]
```
### 10. reverse()
 - Reverses the order of the list in place.
```
my_list = [1, 2, 3]
my_list.reverse()  # my_list becomes [3, 2, 1]
```
### 11. copy()
 - Returns a shallow copy of the list.
```
my_list = [1, 2, 3]
my_copy = my_list.copy()  # my_copy becomes [1, 2, 3]
```
### 12. list()
 - Used to create a new list from an iterable.
```
new_list = list("hello")  # new_list becomes ['h', 'e', 'l', 'l', 'o']
```
### Accessing list values
 - you can also slice lists the way you do with strings
 - you can also insert values this way
```
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
thislist[1:3] = ["blackcurrant", "watermelon"]
print(thislist)
```
 - If you insert more items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
```
thislist = ["apple", "banana", "cherry"]
thislist[1:2] = ["blackcurrant", "watermelon"]
print(thislist)
```
 - If you insert less items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
```
thislist = ["apple", "banana", "cherry"]
thislist[1:3] = ["watermelon"]
print(thislist)
```
### To loop through a list
```
thislist = ["apple", "banana", "cherry"]
for x in thislist:
  print(x)

thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
  print(thislist[i])
  
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
  print(thislist[i])
  i = i + 1

#Using list comprehension
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
```
### List Comprehension
 - Without list comprehension
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []

for x in fruits:
  if "a" in x:
    newlist.append(x)

print(newlist)
```
 - With list comprehension
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if "a" in x]

print(newlist)
```
 - Syntax
     - `newlist = [expression for item in iterable if condition == True]`
 - Examples
```
newlist = [x for x in range(10)]
newlist = [x for x in range(10) if x < 5]
newlist = [x.upper() for x in fruits]
newlist = ['hello' for x in fruits]
newlist = [x if x != "banana" else "orange" for x in fruits]
```

### Sorting Lists
 - sorting a list alphabetically
```
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort()
print(thislist)
```
 - sorting a list numerically
```
thislist = [100, 50, 65, 82, 23]
thislist.sort()
print(thislist)
```
 - to sort in the reverse
```
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort(reverse = True)
print(thislist)
```
 - you can also customize your sort function to work differently
```
def myfunc(n):
  return abs(n - 50)

thislist = [100, 50, 65, 82, 23]
thislist.sort(key = myfunc)
print(thislist)
```
 - When sorting strings, by default capitalized words are placed before lowercase words
 - This is what to do to avoid that
```
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort(key = str.lower)
print(thislist)
```
 - To reverse the order of a list more generally
```
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.reverse()
print(thislist)
```
### Copying lists
 - you can't copy a list by just setting another variable equal to the first list, because it just refers back to the original list, meaning if you change the first list, those changes will be also be added to the second one
```
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)

thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print(mylist)

thislist = ["apple", "banana", "cherry"]
mylist = thislist[:]
print(mylist)
```

### Ways to join lists
```
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)

list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)

list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)
```





















