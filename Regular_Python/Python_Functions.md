# Python Functions

## 1. Defining a Function
 - Use the `def` keyword to define a function.
```
def greet():
    print("Hello, World!")
greet()
# Output: Hello, World!
```
## 2. Function with Parameters
 - Pass arguments to the function for more dynamic behavior.
```
def greet(name):
    print(f"Hello, {name}!")
greet("Alice")
# Output: Hello, Alice!
```
## 3. Function with Default Parameters
 - Provide default values for parameters.
```
def greet(name="World"):
    print(f"Hello, {name}!")
greet()
greet("Bob")
# Output:
# Hello, World!
# Hello, Bob!
```
## 4. Function with Return Value
 - Use `return` to send a result back to the caller.
```
def add(a, b):
    return a + b
result = add(3, 5)
print(result)
# Output: 8
```
## 5. Multiple Return Values
 - Return multiple values as a tuple.
```
def arithmetic(a, b):
    return a + b, a - b, a * b, a / b
add_result, sub_result, mul_result, div_result = arithmetic(10, 2)
print(add_result, sub_result, mul_result, div_result)
# Output: 12 8 20 5.0
```
## 6. Keyword Arguments
 - Pass arguments by name for clarity.
```
def introduce(name, age):
    print(f"My name is {name}, and I am {age} years old.")
introduce(age=30, name="Charlie")
# Output: My name is Charlie, and I am 30 years old.
```
## 7. Arbitrary Arguments (*args)
 - Use `*args` to accept a variable number of positional arguments.
```
def sum_all(*args):
    return sum(args)
result = sum_all(1, 2, 3, 4, 5)
print(result)
# Output: 15
```
## 8. Arbitrary Keyword Arguments (**kwargs)
 - Use `**kwargs` to accept a variable number of keyword arguments.
```
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")
print_info(name="Alice", age=25, city="New York")
# Output:
# name: Alice
# age: 25
# city: New York
```
## 9. Positional-Only Arguments
 - Use `/` to enforce positional-only arguments.
```
def greet(name, /, message):
    print(f"{message}, {name}!")
greet("Alice", "Hello")
# Output: Hello, Alice!
# greet(name="Alice", message="Hello")  # Raises a TypeError
```
## 10. Keyword-Only Arguments
 - Use `*` to enforce keyword-only arguments.
```
def greet(*, name, message):
    print(f"{message}, {name}!")
greet(name="Alice", message="Hello")
# Output: Hello, Alice!
# greet("Alice", "Hello")  # Raises a TypeError
```
## 11. Combined Positional-Only and Keyword-Only
 - Use both `/` and `*` to mix positional-only and keyword-only arguments.
```
def greet(name, /, *, message):
    print(f"{message}, {name}!")
greet("Alice", message="Hello")
# Output: Hello, Alice!
```
## 12. Nested Functions
 - Define a function inside another function.
```
def outer_function(name):
    def inner_function():
        return f"Hello, {name}!"
    return inner_function()
result = outer_function("Alice")
print(result)
# Output: Hello, Alice!
```
## 13. Lambda Functions
 - Anonymous functions created with the `lambda` keyword.
```
square = lambda x: x ** 2
print(square(4))
# Output: 16
```
## 14. Higher-Order Functions
 - Pass functions as arguments to other functions.
```
def apply_function(func, value):
    return func(value)
result = apply_function(lambda x: x ** 2, 5)
print(result)
# Output: 25
```
## 15. Recursive Functions
 - A function that calls itself for solving problems.
```
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n - 1)
print(factorial(5))
# Output: 120
```
## 16. Function Annotations
 - Add type hints for parameters and return values.
```
def greet(name: str) -> str:
    return f"Hello, {name}!"
print(greet("Alice"))
# Output: Hello, Alice!
```
## 17. Pass Statement in Functions
 - Use `pass` as a placeholder for an empty function.
```
def placeholder_function():
    pass  # Placeholder for future implementation
# No output; no error
```
## 18. Docstrings
 - Add a documentation string to describe the purpose of a function.
```
def greet(name):
    """
    Greets a person with their name.
    
    Parameters:
    name (str): The name of the person.
    
    Returns:
    None
    """
    print(f"Hello, {name}!")
greet("Alice")
# Output: Hello, Alice!
```
## 19. Scope and Global Variables
 - Variables defined inside a function are local by default.
 - Use `global` to modify a global variable inside a function.
```
x = 10
def modify_global():
    global x
    x = 20
modify_global()
print(x)
# Output: 20
```
## 20. Using *args and **kwargs Together
 - Combine `*args` and `**kwargs` to accept all types of arguments.
```
def flexible_function(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)
flexible_function(1, 2, 3, name="Alice", age=25)
# Output:
# Positional arguments: (1, 2, 3)
# Keyword arguments: {'name': 'Alice', 'age': 25}
```
