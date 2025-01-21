# Python For Loops Guide

## 1. Basic `For` Loop
 - Iterates over a sequence (like a list, tuple, or string).
```
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    print(num)
# Output:
# 1
# 2
# 3
# 4
# 5
```
## 2. Iterating Over a String
 - Loops through each character in a string.
```
text = "Hello"
for char in text:
    print(char)
# Output:
# H
# e
# l
# l
# o
```
## 3. Using `Range()`
 - Use `range()` to generate a sequence of numbers.
```
for i in range(5):
    print(i)
# Output:
# 0
# 1
# 2
# 3
# 4
```
 - Specifying a start, stop, and step.
```
for i in range(2, 10, 2):
    print(i)
# Output:
# 2
# 4
# 6
# 8
```
## 4. Nested `For` Loops
 - A for loop inside another for loop.
```
for i in range(3):
    for j in range(2):
        print(f"Outer: {i}, Inner: {j}")
# Output:
# Outer: 0, Inner: 0
# Outer: 0, Inner: 1
# Outer: 1, Inner: 0
# Outer: 1, Inner: 1
# Outer: 2, Inner: 0
# Outer: 2, Inner: 1
```
## 5. Using `Break` in `For` Loops
 - Exits the loop immediately when `break` is executed.
```
for num in range(10):
    if num == 5:
        break
    print(num)
# Output:
# 0
# 1
# 2
# 3
# 4
```
## 6. Using `Continue` in `For` Loops
 - Skips the rest of the current iteration and moves to the next one.
```
for num in range(5):
    if num == 2:
        continue
    print(num)
# Output:
# 0
# 1
# 3
# 4
```
## 7. Using Else with For Loops
 - Executes the `else` block if the loop completes naturally (without `break`).
```
for num in range(3):
    print(num)
else:
    print("Loop finished!")
# Output:
# 0
# 1
# 2
# Loop finished!
```
## 8. Looping Over a Dictionary
 - Iterate through keys, values, or key-value pairs.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}

# Looping through keys
for key in my_dict:
    print(key)
# Output:
# name
# age
# city

# Looping through values
for value in my_dict.values():
    print(value)
# Output:
# Alice
# 25
# New York

# Looping through key-value pairs
for key, value in my_dict.items():
    print(key, value)
# Output:
# name Alice
# age 25
# city New York
```
## 9. Using `Enumerate`
 - Get the index and value while iterating through a sequence.
```
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
# Output:
# 0 apple
# 1 banana
# 2 cherry
```
## 10. Using `Zip`
 - Loop through multiple sequences simultaneously.
```
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
for name, age in zip(names, ages):
    print(name, age)
# Output:
# Alice 25
# Bob 30
# Charlie 35
```
## 11. Iterating with a Step
 - Use slicing to step through a list.
```
numbers = [0, 1, 2, 3, 4, 5, 6]
for num in numbers[::2]:
    print(num)
# Output:
# 0
# 2
# 4
# 6
```
## 12. `Pass` in For Loops
 - Use `pass` as a placeholder to create an empty loop.
```
for num in range(3):
    pass  # Placeholder for future code
# No output; no error
```
## 13. Simulating Reverse Iteration
 - Use `reversed()` to iterate in reverse order.
```
for num in reversed(range(5)):
    print(num)
# Output:
# 4
# 3
# 2
# 1
# 0
```
