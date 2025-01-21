# Python Lambda Functions

## 1. Basic Lambda Function
 - A lambda function is an anonymous function defined using the `lambda` keyword.
 - Syntax: `lambda arguments: expression`
```
square = lambda x: x ** 2
print(square(4))
# Output: 16
```
## 2. Lambda with Multiple Arguments
 - Lambda functions can take multiple arguments.
```
add = lambda a, b: a + b
print(add(3, 5))
# Output: 8
```
## 3. Using Lambda in a Function
 - Lambda functions can be defined inside regular functions.
```
def multiplier(factor):
    return lambda x: x * factor
double = multiplier(2)
print(double(5))
# Output: 10
```
## 4. Lambda with Default Arguments
 - Lambda functions can have default parameter values.
```
power = lambda base, exponent=2: base ** exponent
print(power(3))  # Output: 9
print(power(3, 3))  # Output: 27
```
## 5. Lambda in Higher-Order Functions
 - Use lambda functions with higher-order functions like `map()`, `filter()`, and `reduce()`.
```
numbers = [1, 2, 3, 4, 5]

# Example with map()
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)
# Output: [1, 4, 9, 16, 25]

# Example with filter()
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)
# Output: [2, 4]

# Example with reduce()
from functools import reduce
product = reduce(lambda x, y: x * y, numbers)
print(product)
# Output: 120
```
## 6. Lambda with Conditional Expressions
 - Use conditional expressions in lambda functions for dynamic behavior.
```
maximum = lambda a, b: a if a > b else b
print(maximum(10, 20))
# Output: 20
```
## 7. Lambda in Sorting
 - Use lambda functions as the `key` argument in sorting functions.
```
people = [{"name": "Alice", "age": 25}, {"name": "Bob", "age": 30}, {"name": "Charlie", "age": 20}]
sorted_people = sorted(people, key=lambda person: person["age"])
print(sorted_people)
# Output: [{'name': 'Charlie', 'age': 20}, {'name': 'Alice', 'age': 25}, {'name': 'Bob', 'age': 30}]
```
## 8. Lambda for String Manipulation
 - Use lambda functions for string transformations.
```
to_upper = lambda s: s.upper()
print(to_upper("hello"))
# Output: HELLO
```
## 9. Lambda in Dictionaries
 - Use lambda functions for values in a dictionary.
```
operations = {
    "add": lambda x, y: x + y,
    "subtract": lambda x, y: x - y,
    "multiply": lambda x, y: x * y,
    "divide": lambda x, y: x / y if y != 0 else "Division by zero"
}
print(operations["add"](10, 5))  # Output: 15
print(operations["divide"](10, 0))  # Output: Division by zero
```
## 10. Limitations of Lambda Functions
 - Lambda functions are limited to a single expression.
- Use regular functions (`def`) for complex logic.
```
# Example:
# This is valid for lambda:
simple = lambda x: x + 1

# This is not valid:
# complex_lambda = lambda x: x + 1; print(x)
```
## 11. Lambda with Enumerate
 - Combine `lambda` with `enumerate()` for indexed operations.
```
numbers = [10, 20, 30]
indexed_operations = list(map(lambda x: x[0] * x[1], enumerate(numbers)))
print(indexed_operations)
# Output: [0, 20, 60]
```
## 12. Lambda and List Comprehension
 - Use lambda functions inside list comprehensions.
```
numbers = [1, 2, 3, 4, 5]
cubed_numbers = [(lambda x: x ** 3)(num) for num in numbers]
print(cubed_numbers)
# Output: [1, 8, 27, 64, 125]
```
## 13. Lambda with Type Hints
 - You can add type hints for clarity when using lambda functions.
```
add: callable = lambda a: a + 10
print(add(5))  # Output: 15
```
## 14. Pass Lambda to Functions
 - Pass lambda as a parameter to other functions.
```
def apply_operation(operation, x, y):
    return operation(x, y)
result = apply_operation(lambda a, b: a * b, 3, 5)
print(result)
# Output: 15
```
