# Python Iterators

## 1. What is an Iterator?
 - An iterator is an object that represents a sequence of values and allows you to traverse through it one value at a time.
 - Iterators are implemented with two main methods: `__iter__()` and `__next__()`.


## 2. Iterables vs. Iterators
 - An **iterable** is an object that can return an iterator, such as a list, tuple, or string.
 - An **iterator** is the object returned by calling `iter()` on an iterable.

- Example of an iterable and its iterator:
```
my_list = [1, 2, 3]
iterator = iter(my_list)  # Convert iterable to iterator
print(next(iterator))  # Output: 1
print(next(iterator))  # Output: 2
print(next(iterator))  # Output: 3
# print(next(iterator))  # Raises StopIteration
```

## 3. Creating an Iterator from Scratch
 - Create a class with `__iter__()` and `__next__()` methods.
```
class Counter:
    def __init__(self, limit):
        self.limit = limit
        self.count = 0

    def __iter__(self):
        return self  # The object itself is an iterator

    def __next__(self):
        if self.count < self.limit:
            self.count += 1
            return self.count
        else:
            raise StopIteration

counter = Counter(3)
for num in counter:
    print(num)
# Output:
# 1
# 2
# 3
```

## 4. Using Iterators with Built-In Functions
 - Many built-in functions work with iterators.
```
# Example: `range()` is an iterable
for num in range(5):
    print(num)
# Output:
# 0
# 1
# 2
# 3
# 4

# Converting an iterator to a list
iterator = iter(range(3))
print(list(iterator))  # Output: [0, 1, 2]
```

## 5. Iterators with Custom Logic
 - Use iterators to implement custom behavior.
```
class Fibonacci:
    def __init__(self, max_terms):
        self.max_terms = max_terms
        self.first = 0
        self.second = 1
        self.count = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.count >= self.max_terms:
            raise StopIteration
        if self.count == 0:
            self.count += 1
            return self.first
        elif self.count == 1:
            self.count += 1
            return self.second
        else:
            self.count += 1
            self.first, self.second = self.second, self.first + self.second
            return self.second

fib = Fibonacci(5)
print(list(fib))
# Output: [0, 1, 1, 2, 3]
```

## 6. Using `iter()` with Sentinel Values
 - Use `iter()` with a sentinel value to stop iteration when a condition is met.
```
# Example: Reading lines from a file
with open("example.txt", "w") as f:
    f.write("line1\nline2\nline3")

with open("example.txt") as f:
    for line in iter(f.readline, ''):
        print(line.strip())
# Output:
# line1
# line2
# line3
```

## 7. Infinite Iterators with `itertools`
 - Use the `itertools` module to create iterators for advanced use cases.
```
from itertools import count, cycle, repeat

# Infinite counter
for num in count(10):  # Starts at 10
    if num > 15:
        break
    print(num)
# Output: 10, 11, 12, 13, 14, 15

# Cycling through a sequence
for char in cycle("ABC"):
    print(char)
    break  # Use break to avoid infinite loop

# Repeating a value
for value in repeat("Hello", 3):
    print(value)
# Output:
# Hello
# Hello
# Hello
```

## 8. Generators as Iterators
 - Generators are a simpler way to create iterators using the `yield` keyword.
```
def simple_generator():
    yield 1
    yield 2
    yield 3

gen = simple_generator()
print(next(gen))  # Output: 1
print(next(gen))  # Output: 2
print(next(gen))  # Output: 3
# print(next(gen))  # Raises StopIteration

# Generators are iterable
for value in simple_generator():
    print(value)
# Output:
# 1
# 2
# 3
```

## 9. Checking if an Object is an Iterable or Iterator
 - Use `isinstance()` with `collections.abc` to check.
```
from collections.abc import Iterable, Iterator

my_list = [1, 2, 3]
iterator = iter(my_list)

print(isinstance(my_list, Iterable))  # Output: True
print(isinstance(my_list, Iterator))  # Output: False

print(isinstance(iterator, Iterator))  # Output: True
```
