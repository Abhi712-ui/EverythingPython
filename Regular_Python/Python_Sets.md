# Python Sets
- `myset = {"apple", "banana", "cherry"}`
- sets are unordered, unindexed, and unchangeable
- set items are unchangeable, but you can still add or remove new items
- since sets are unordered, the values can appear in different orders each time you see them
- sets cannot have duplicates
- python will simply ignore the duplicate values
- True and 1 are considered duplicate values, while 0 and False are also considered duplicate values
- sets can also contain variables of different data types together
- sets use many of the same functions that lists do as well
- you can use a constructor to create a set
```
thisset = set(("apple", "banana", "cherry")) # note the double round-brackets
print(thisset)
```
- you can access set values in most of the same ways that you do with lists, but you cannot reference them by index, since the set is unordered
- you can loop through a set using a for loop
```
thisset = {"apple", "banana", "cherry"}
for x in thisset:
  print(x)
```
## Adding items to sets
```
thisset = {"apple", "banana", "cherry"}
thisset.add("orange")
print(thisset)

thisset = {"apple", "banana", "cherry"}
tropical = {"pineapple", "mango", "papaya"}
thisset.update(tropical)
print(thisset)

thisset = {"apple", "banana", "cherry"}
mylist = ["kiwi", "orange"]
thisset.update(mylist)
print(thisset)
```
## removing items from sets
```
thisset = {"apple", "banana", "cherry"}
thisset.remove("banana")
print(thisset)

thisset = {"apple", "banana", "cherry"}
thisset.discard("banana")
print(thisset)
```
- you can also use the `pop()` method, but that will remove a random value from the set
- `clear()` will empty the set, while `del` will delete the set completely
## Joining sets
- `union()` - returns a set that is a combination of 2 or more sets
- you can also do this using the `|` operator
```
set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set3 = {"John", "Elena"}
set4 = {"apple", "bananas", "cherry"}

myset = set1.union(set2, set3, set4)
print(myset)

set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set3 = {"John", "Elena"}
set4 = {"apple", "bananas", "cherry"}

myset = set1 | set2 | set3 |set4
print(myset)
```
- you can also join a set and a tuple, creating a new set
```
x = {"a", "b", "c"}
y = (1, 2, 3)
z = x.union(y)
print(z)
```
- `|` only lets you join sets together, not anything else
- the `update()` method lets you add all the elements of one set to another, it only modifies a set and does not return a new set like the `union()` method does
```
set1 = {"a", "b" , "c"}
set2 = {1, 2, 3}
set1.update(set2)
print(set1)
```
- the `intersection()` method will return a new set that contains all of the elements that occur in the set(s) that you passed in
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.intersection(set2)
print(set3)
```
- you can also use the `&` operator to get the same result
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1 & set2
print(set3)
```
- like previously, you can only use the `&` operator for intersections between other sets, whereas you can use the `intersection()` method for intersections between sets and other data types
- The `intersection_update()` method does the same thing, but updates the set you use it on, rather than creating a new set
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set1.intersection_update(set2)
print(set1)
```
- like before, `True` and `1` are considered to be duplicates, as is also the case with `False` and `0`
- the `difference()` method returns a new set with all of the items from the first set that are not present in the other set
- you can also do this using the `-` operator, but that only works on sets, and not between a set and a different data structure
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.difference(set2)
print(set3)

set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1 - set2
print(set3)
```
- there is also `difference_update()`
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set1.difference_update(set2)
print(set1)
```
- there also exists `symmetric_difference()`
- it keeps the elements that are not present in both sets
- also signified using the `^` operator
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.symmetric_difference(set2)
print(set3)

set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1 ^ set2
print(set3)
```
- then there is also `symmetric_difference_update()`
```
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set1.symmetric_difference_update(set2)
print(set1)
```

## Set Methods in Python and Equivalent Operators

### `add()`
- Adds an element to the set.
```
my_set = {1, 2, 3}
my_set.add(4)  # my_set becomes {1, 2, 3, 4}
```
### `remove()`
- Removes a specified element from the set; raises KeyError if the element is not found.
```
my_set = {1, 2, 3}
my_set.remove(2)  # my_set becomes {1, 3}
```
### `discard()`
- Removes a specified element from the set; does not raise an error if the element is not found.
```
my_set = {1, 2, 3}
my_set.discard(2)  # my_set becomes {1, 3}
my_set.discard(4)  # No error, my_set remains {1, 3}
```
### `pop()`
- Removes and returns an arbitrary element from the set.
```
my_set = {1, 2, 3}
element = my_set.pop()  # Returns an arbitrary element (e.g., 1); my_set is now smaller.
```
### `clear()`
- Removes all elements from the set.
```
my_set = {1, 2, 3}
my_set.clear()  # my_set becomes set()
```
### `union()`
- Returns a set containing all unique elements from both sets.
```
# Operator: |
set1 = {1, 2}
set2 = {3, 4}
result = set1.union(set2)  # result becomes {1, 2, 3, 4}
result = set1 | set2       # Equivalent to union()
```
### `intersection()`
- Returns a set containing elements common to both sets.
```
# Operator: &
set1 = {1, 2, 3}
set2 = {2, 3, 4}
result = set1.intersection(set2)  # result becomes {2, 3}
result = set1 & set2              # Equivalent to intersection()
```
### `difference()`
- Returns a set containing elements in the first set but not in the second.
```
# Operator: -
set1 = {1, 2, 3}
set2 = {2, 3, 4}
result = set1.difference(set2)  # result becomes {1}
result = set1 - set2            # Equivalent to difference()
```
### `symmetric_difference()`
- Returns a set containing elements in either set, but not in both.
```
# Operator: ^
set1 = {1, 2, 3}
set2 = {2, 3, 4}
result = set1.symmetric_difference(set2)  # result becomes {1, 4}
result = set1 ^ set2                      # Equivalent to symmetric_difference()
```
### `update()`
- Updates the set with the union of itself and another set.
```
# Operator: |=
set1 = {1, 2}
set2 = {3, 4}
set1.update(set2)  # set1 becomes {1, 2, 3, 4}
set1 |= set2       # Equivalent to update()
```
### `intersection_update()`
- Updates the set with the intersection of itself and another set.
```
# Operator: &=
set1 = {1, 2, 3}
set2 = {2, 3, 4}
set1.intersection_update(set2)  # set1 becomes {2, 3}
set1 &= set2                    # Equivalent to intersection_update()
```
### `difference_update()`
- Updates the set with the difference of itself and another set.
```
# Operator: -=
set1 = {1, 2, 3}
set2 = {2, 3, 4}
set1.difference_update(set2)  # set1 becomes {1}
set1 -= set2                  # Equivalent to difference_update()
```
### `symmetric_difference_update()`
- Updates the set with the symmetric difference of itself and another set.
```
# Operator: ^=
set1 = {1, 2, 3}
set2 = {2, 3, 4}
set1.symmetric_difference_update(set2)  # set1 becomes {1, 4}
set1 ^= set2                            # Equivalent to symmetric_difference_update()
```
### `isdisjoint()`
- Returns `True` if the sets have no common elements.
```
set1 = {1, 2, 3}
set2 = {4, 5, 6}
result = set1.isdisjoint(set2)  # Returns True
```
### `issubset()`
- Returns `True` if the set is a subset of another set.
```
# Operator: <=
set1 = {1, 2}
set2 = {1, 2, 3}
result = set1.issubset(set2)  # Returns True
result = set1 <= set2         # Equivalent to issubset()
```
### `issuperset()`
- Returns True if the set is a superset of another set.
```
# Operator: >=
set1 = {1, 2, 3}
set2 = {1, 2}
result = set1.issuperset(set2)  # Returns True
result = set1 >= set2           # Equivalent to issuperset()
```
