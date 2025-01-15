# Python While Loops

### 1. Basic `While` Loop
 - Repeats a block of code as long as the condition is True.
```
x = 0
while x < 5:
    print(x)
    x += 1
# Output:
# 0
# 1
# 2
# 3
# 4
```
### 2. Infinite While Loop
 - A loop that runs indefinitely if the condition is always True.
 - Use with caution, and include a way to break out of the loop.
```
while True:
    print("This will run forever!")
    break  # Stops the infinite loop
# Output: This will run forever!
```
### 3. Using Break in a While Loop
 - Exits the loop immediately when `break` is executed.
```
x = 0
while x < 10:
    if x == 5:
        break
    print(x)
    x += 1
# Output:
# 0
# 1
# 2
# 3
# 4
```
### 4. Using Continue in a While Loop
 - Skips the rest of the current iteration and moves to the next one.
```
x = 0
while x < 5:
    x += 1
    if x == 3:
        continue
    print(x)
# Output:
# 1
# 2
# 4
# 5
```
### 5. Using `Else` with `While`
 - Executes the `else` block when the loop finishes naturally (without a `break`).
```
x = 0
while x < 5:
    print(x)
    x += 1
else:
    print("Loop finished!")
# Output:
# 0
# 1
# 2
# 3
# 4
# Loop finished!
```
### 6. Nested `While` Loops
 - A while loop inside another while loop.
```
outer = 0
while outer < 3:
    inner = 0
    while inner < 2:
        print(f"Outer: {outer}, Inner: {inner}")
        inner += 1
    outer += 1
# Output:
# Outer: 0, Inner: 0
# Outer: 0, Inner: 1
# Outer: 1, Inner: 0
# Outer: 1, Inner: 1
# Outer: 2, Inner: 0
# Outer: 2, Inner: 1
```
### 7. Avoiding Infinite Loops
 - Ensure that the condition eventually becomes False.
```
x = 10
while x > 0:
    print(x)
    x -= 2
# Output:
# 10
# 8
# 6
# 4
# 2
```
### 8. Using Logical Conditions in While
 - Combine multiple conditions with `and`, `or`, and `not`.
```
x = 0
while x < 10 and x % 2 == 0:
    print(x)
    x += 2
# Output:
# 0
# 2
# 4
# 6
# 8
```
### 9. Using Pass in While Loops
 - Use `pass` as a placeholder to create an empty loop.
```
x = 0
while x < 5:
    pass  # Placeholder for future code
# No output; no error
```
### 10. Simulating Do-While Behavior
 - Python doesn’t have a built-in do-while loop, but you can simulate it.
```
x = 0
while True:
    print(x)
    x += 1
    if x >= 5:
        break
# Output:
# 0
# 1
# 2
# 3
# 4
```
