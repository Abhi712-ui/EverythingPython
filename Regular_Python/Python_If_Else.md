# Python If-Else

## 1. Simple `if` Statement
 - Executes a block of code if the condition is True.
```
x = 10
if x > 5:
    print("x is greater than 5")
# Output: x is greater than 5
```
## 2. `if-else` Statement
 - Executes one block of code if the condition is True, and another block if it's False.
```
x = 3
if x > 5:
    print("x is greater than 5")
else:
    print("x is not greater than 5")
# Output: x is not greater than 5
```
## 3. `if`-`elif`-`else` Statement
 - Allows you to check multiple conditions.
```
x = 10
if x < 5:
    print("x is less than 5")
elif x == 10:
    print("x is equal to 10")
else:
    print("x is greater than 5 but not equal to 10")
# Output: x is equal to 10
```
## 4. Nested `if` Statement
 - An if statement inside another if statement.
```
x = 15
if x > 10:
    if x < 20:
        print("x is between 10 and 20")
# Output: x is between 10 and 20
```
## 5. Short-Hand `if` Statement
 - One-liner if statement for simple conditions.
```
x = 10
if x > 5: print("x is greater than 5")
# Output: x is greater than 5
```
## 6. Short-Hand `if`-`else` Statement (Ternary Operator)
 - One-liner if-else statement for compact code.
```
x = 10
print("x is greater than 5") if x > 5 else print("x is not greater than 5")
# Output: x is greater than 5
```
## 7. Logical Operators in `if` Statements
 - Combine multiple conditions using `and`, `or`, and `not`.
```
x = 15
if x > 10 and x < 20:
    print("x is between 10 and 20")
# Output: x is between 10 and 20

if x < 10 or x > 20:
    print("x is outside the range")
else:
    print("x is within the range")
# Output: x is within the range

if not (x < 10):
    print("x is not less than 10")
# Output: x is not less than 10
```
## 8. Comparing Multiple Values
 - Use chained comparisons for cleaner code.
```
x = 15
if 10 < x < 20:
    print("x is between 10 and 20")
# Output: x is between 10 and 20
```
## 9. Pass Statement in `if`
 - Use `pass` to create an empty if block as a placeholder.
```
x = 10
if x > 5:
    pass  # Placeholder for future code
# No output; no error
```
## 10. Using `if`-`else` in a Function
 - Use conditional statements to return different values from a function.
```
def check_number(x):
    if x > 0:
        return "Positive"
    elif x < 0:
        return "Negative"
    else:
        return "Zero"

print(check_number(5))   # Output: Positive
print(check_number(-2))  # Output: Negative
print(check_number(0))   # Output: Zero
```
