# Python Lists
- `mylist = ["apple", "banana", "cherry"]`
- used to store multiple values in python
- one of four main data structures, which are lists, tuples, sets, and dicts
- created using square brackets
- ordered, meaning that new elements will always be added to the end of the list
- lists are also changable and can contain duplicates
- also uses `len`
- can contain multiple different data types in one list

## List Methods in Python

## 1. `append()`
- Adds an element to the end of the list.
```
my_list = [1, 2, 3]
my_list.append(4)  # my_list becomes [1, 2, 3, 4]
```

## 2. `extend()`
- Extends the list by appending elements from another iterable.
- Can also take in another iterable to be added to the list
```
my_list = [1, 2, 3]
my_list.extend([4, 5])  # my_list becomes [1, 2, 3, 4, 5]
```
## 3. `insert()`
- Inserts an element at a specified position.
```
my_list = [1, 2, 4]
my_list.insert(2, 3)  # my_list becomes [1, 2, 3, 4]
```
## 4. `remove()`
- Removes the first occurrence of a specified value.
- Alternatively, the del function could be used to remove a specific value from the list, taking in the index of the value
- The del keyword can also delete the list completely
```
my_list = [1, 2, 3, 2]
my_list.remove(2)  # my_list becomes [1, 3, 2]
del thislist[0]
```
## 5. `pop()`
- Removes and returns the element at a specified index (default is the last).
```
my_list = [1, 2, 3]
my_list.pop()     # Returns 3; my_list becomes [1, 2]
my_list.pop(0)    # Returns 1; my_list becomes [2]
```
## 6. `clear()`
- Removes all elements from the list.
```
my_list = [1, 2, 3]
my_list.clear()   # my_list becomes []
```
## 7. `index()`
- Returns the index of the first occurrence of a specified value.
```
my_list = [1, 2, 3, 2]
my_list.index(2)  # Returns 1
my_list.index(2, 2)  # Returns 3 (start search at index 2)
```
## 8. `count()`
- Returns the number of occurrences of a specified value.
```
my_list = [1, 2, 3, 2]
my_list.count(2)  # Returns 2
```
## 9. `sort()`
- Sorts the list in ascending order (by default).
```
my_list = [3, 1, 2]
my_list.sort()    # my_list becomes [1, 2, 3]
my_list.sort(reverse=True)  # my_list becomes [3, 2, 1]
```
## 10. reverse()
- Reverses the order of the list in place.
```
my_list = [1, 2, 3]
my_list.reverse()  # my_list becomes [3, 2, 1]
```
## 11. `copy()`
- Returns a shallow copy of the list.
```
my_list = [1, 2, 3]
my_copy = my_list.copy()  # my_copy becomes [1, 2, 3]
```
## 12. `list()`
- Used to create a new list from an iterable.
```
new_list = list("hello")  # new_list becomes ['h', 'e', 'l', 'l', 'o']
```
## Accessing list values
- you can also slice lists the way you do with strings
- you can also insert values this way
```
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
thislist[1:3] = ["blackcurrant", "watermelon"]
print(thislist)
```
- If you insert more items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
```
thislist = ["apple", "banana", "cherry"]
thislist[1:2] = ["blackcurrant", "watermelon"]
print(thislist)
```
- If you insert less items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
```
thislist = ["apple", "banana", "cherry"]
thislist[1:3] = ["watermelon"]
print(thislist)
```
## To loop through a list
```
thislist = ["apple", "banana", "cherry"]
for x in thislist:
  print(x)

thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
  print(thislist[i])
  
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
  print(thislist[i])
  i = i + 1

#Using list comprehension
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
```
## List Comprehension
- Without list comprehension
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []

for x in fruits:
  if "a" in x:
    newlist.append(x)

print(newlist)
```
- With list comprehension
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if "a" in x]

print(newlist)
```
- Syntax
    - `newlist = [expression for item in iterable if condition == True]`
- Examples
```
newlist = [x for x in range(10)]
newlist = [x for x in range(10) if x < 5]
newlist = [x.upper() for x in fruits]
newlist = ['hello' for x in fruits]
newlist = [x if x != "banana" else "orange" for x in fruits]
```

## Sorting Lists
- sorting a list alphabetically
```
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort()
print(thislist)
```
- sorting a list numerically
```
thislist = [100, 50, 65, 82, 23]
thislist.sort()
print(thislist)
```
- to sort in the reverse
```
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort(reverse = True)
print(thislist)
```
- you can also customize your sort function to work differently
```
def myfunc(n):
  return abs(n - 50)

thislist = [100, 50, 65, 82, 23]
thislist.sort(key = myfunc)
print(thislist)
```
- When sorting strings, by default capitalized words are placed before lowercase words
- This is what to do to avoid that
```
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort(key = str.lower)
print(thislist)
```
- To reverse the order of a list more generally
```
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.reverse()
print(thislist)
```
## Copying lists
- you can't copy a list by just setting another variable equal to the first list, because it just refers back to the original list, meaning if you change the first list, those changes will be also be added to the second one
```
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)

thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print(mylist)

thislist = ["apple", "banana", "cherry"]
mylist = thislist[:]
print(mylist)
```

## Ways to join lists
```
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)

list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)

list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)
```
