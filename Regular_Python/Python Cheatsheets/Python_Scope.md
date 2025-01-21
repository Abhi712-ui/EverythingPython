# Python Scope

## 1. What is Scope?
 - Scope defines the region where a variable can be accessed.
 - Variables can be:
   - **Local**: Defined inside a function or block.
   - **Global**: Defined at the top level of a script or module.
   - **Nonlocal**: Used in nested functions, referring to variables in the enclosing function's scope.


## 2. Local Scope
 - Variables declared inside a function are local to that function.
```
def my_function():
    x = 10  # Local variable
    print(x)

my_function()
# Output: 10
# print(x)  # Error: NameError: name 'x' is not defined
```

## 3. Global Scope
 - Variables declared outside any function or block have global scope.
 - They are accessible anywhere in the script.
```
x = 20  # Global variable

def my_function():
    print(x)  # Accessing the global variable inside a function

my_function()
# Output: 20
```

## 4. Modifying Global Variables
 - Use the `global` keyword to modify a global variable inside a function.
```
x = 10

def modify_global():
    global x  # Declaring x as global
    x = 20

modify_global()
print(x)  # Output: 20
```

## 5. Enclosing (Nonlocal) Scope
 - Refers to the scope of an enclosing function in nested functions.
 - Use the `nonlocal` keyword to modify variables in the enclosing scope.
```
def outer_function():
    x = "Outer variable"

    def inner_function():
        nonlocal x  # Refers to the outer_function's x
        x = "Modified by inner"
    
    inner_function()
    print(x)

outer_function()
# Output: Modified by inner
```

## 6. Built-in Scope
 - Refers to Python's built-in names like `len()` or `print()`.
```
print(len("Hello"))  # Output: 5

# Example of overriding built-in scope (not recommended)
len = 10
# print(len("Hello"))  # Error: TypeError: 'int' object is not callable
del len  # Restore the built-in name
```

## 7. Scope Resolution with LEGB Rule
 - Python resolves variables using the **LEGB** rule:
   - **L**: Local — Variables inside the current function.
   - **E**: Enclosing — Variables in the enclosing function (nested).
   - **G**: Global — Variables defined at the script's top level.
   - **B**: Built-in — Python’s built-in functions and constants.

- Example of LEGB in action:
```
x = "Global"

def outer_function():
    x = "Enclosing"

    def inner_function():
        x = "Local"
        print(x)  # Resolves to local variable

    inner_function()
    print(x)  # Resolves to enclosing variable

outer_function()
print(x)  # Resolves to global variable

# Output:
# Local
# Enclosing
# Global
```
---

## 8. Variable Shadowing
 - A variable in an inner scope can shadow (hide) a variable in an outer scope.
```
x = 50

def shadow_example():
    x = 10  # Shadows the global variable
    print(x)

shadow_example()
print(x)  # Global variable remains unchanged
# Output:
# 10
# 50
```
---

## 9. Nested Functions and Scope
 - Inner functions can access variables from the outer function using enclosing scope.
```
def outer_function():
    message = "Outer scope variable"

    def inner_function():
        print(message)  # Accesses outer scope variable
    
    inner_function()

outer_function()
# Output: Outer scope variable
```

## 10. Common Errors in Scope
 - **UnboundLocalError**:
   - Occurs when a local variable is used before being assigned.
```
x = 10

def example_error():
    # x += 1  # Error: UnboundLocalError
    pass

# Fix:
def example_fix():
    global x
    x += 1

example_fix()
print(x)  # Output: 11
```

## 11. Best Practices with Scope
- **Avoid excessive use of global variables**:
  - Makes code harder to debug and maintain.
- **Use meaningful variable names**:
  - Avoid shadowing built-in names like `len`, `list`, etc.
- **Use local variables when possible**:
  - Reduces side effects and keeps functions self-contained.

