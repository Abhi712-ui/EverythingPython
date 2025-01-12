# Basic Info
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



















