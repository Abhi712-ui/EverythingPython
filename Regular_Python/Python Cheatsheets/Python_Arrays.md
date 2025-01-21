# Using Lists as Arrays in Python

## 1. Creating a List
 - Use square brackets `[]` to create a list, which serves as an array in Python.
```
array = [1, 2, 3, 4, 5]
print(array)
# Output: [1, 2, 3, 4, 5]
```
## 2. Accessing Elements
 - Access elements using their index (0-based).
```
array = [10, 20, 30, 40]
print(array[0])  # Output: 10
print(array[-1])  # Output: 40 (last element)
```
## 3. Modifying Elements
 - Assign a new value to an element using its index.
```
array = [1, 2, 3]
array[1] = 99
print(array)
# Output: [1, 99, 3]
```
## 4. Adding Elements
 - Use `append()` to add a single element at the end.
```
array = [1, 2, 3]
array.append(4)
print(array)
# Output: [1, 2, 3, 4]
```
 - Use `extend()` to add multiple elements.
```
array.extend([5, 6])
print(array)
# Output: [1, 2, 3, 4, 5, 6]
```
 - Use `insert()` to add an element at a specific index.
```
array.insert(2, 99)
print(array)
# Output: [1, 2, 99, 3, 4, 5, 6]
```
## 5. Removing Elements
 - Use `remove()` to remove the first occurrence of a value.
```
array = [1, 2, 3, 2]
array.remove(2)
print(array)
# Output: [1, 3, 2]
```
 - Use `pop()` to remove an element by index and return it.
```
array = [10, 20, 30]
removed_element = array.pop(1)
print(removed_element)  # Output: 20
print(array)  # Output: [10, 30]
```
 - Use `clear()` to remove all elements from the list.
```
array.clear()
print(array)
# Output: []
```
## 6. Slicing Lists
 - Use slicing to access a subset of the list.
```
array = [10, 20, 30, 40, 50]
print(array[1:4])  # Output: [20, 30, 40]
print(array[:3])   # Output: [10, 20, 30]
print(array[::2])  # Output: [10, 30, 50]
```
## 7. Iterating Over a List
 - Use a for loop to iterate over elements.
```
array = [1, 2, 3, 4]
for element in array:
    print(element)
# Output:
# 1
# 2
# 3
# 4
```
## 8. Checking Membership
 - Use the `in` operator to check if an element exists in the list.
```
array = [1, 2, 3, 4]
print(3 in array)  # Output: True
print(5 in array)  # Output: False
```
## 9. Sorting Lists
 - Use `sort()` to sort the list in place.
```
array = [4, 1, 3, 2]
array.sort()
print(array)
# Output: [1, 2, 3, 4]
```
 - Use `sorted()` to return a new sorted list.
```
array = [4, 1, 3, 2]
sorted_array = sorted(array)
print(sorted_array)
# Output: [1, 2, 3, 4]
```
## 10. Reversing Lists
 - Use `reverse()` to reverse the list in place.
```
array = [1, 2, 3, 4]
array.reverse()
print(array)
# Output: [4, 3, 2, 1]
```
 - Use slicing to create a reversed copy.
```
reversed_array = array[::-1]
print(reversed_array)
# Output: [1, 2, 3, 4]
```
## 11. List Comprehensions
 - Create lists in a concise way.
```
array = [x ** 2 for x in range(5)]
print(array)
# Output: [0, 1, 4, 9, 16]
```
 - Add conditions in list comprehensions.
```
array = [x for x in range(10) if x % 2 == 0]
print(array)
# Output: [0, 2, 4, 6, 8]
```
## 12. Copying Lists
 - Use slicing to create a shallow copy.
```
array = [1, 2, 3]
copy_array = array[:]
print(copy_array)
# Output: [1, 2, 3]
```
 - Use the `copy()` method.
```
copy_array = array.copy()
print(copy_array)
# Output: [1, 2, 3]
```
## 13. Nested Lists
 - Create and access elements in nested lists.
```
nested_list = [[1, 2], [3, 4], [5, 6]]
print(nested_list[1][0])  # Output: 3
```
 - Iterate over nested lists.
```
for sublist in nested_list:
    for item in sublist:
        print(item)
# Output:
# 1
# 2
# 3
# 4
# 5
# 6
```
## 14. Combining Lists
 - Use `+` to concatenate lists.
```
array1 = [1, 2, 3]
array2 = [4, 5, 6]
combined = array1 + array2
print(combined)
# Output: [1, 2, 3, 4, 5, 6]
```
 - Use `*` for repetition.
```
repeated = array1 * 3
print(repeated)
# Output: [1, 2, 3, 1, 2, 3, 1, 2, 3]
```
## 15. Finding the Length
 - Use `len()` to find the number of elements.
```
array = [1, 2, 3, 4]
print(len(array))
# Output: 4
```
## 16. Min, Max, and Sum
 - Use `min()`, `max()`, and `sum()` to perform operations on lists.
```
array = [1, 2, 3, 4]
print(min(array))  # Output: 1
print(max(array))  # Output: 4
print(sum(array))  # Output: 10
```
