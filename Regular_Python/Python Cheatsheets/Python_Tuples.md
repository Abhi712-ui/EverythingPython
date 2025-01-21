# Tuples
```
mytuple = ("apple", "banana", "cherry")
```
- ordered and unchangeable
- allows for duplicates
- to create a tuple with one item, you need to input that item, and then a comma
```
thistuple = ("apple",)
print(type(thistuple))

#NOT a tuple
thistuple = ("apple")
print(type(thistuple))
```
- like lists, tuples can contain multiple different data types together
- you can also create a tuple using the tuple constructor
```
thistuple = tuple(("apple", "banana", "cherry")) # note the double round-brackets
print(thistuple)
```
- tuples can be accessed the same way you would access a list
- you can't add values directly to a tuple, but you can convert it into a list, add items to that list, and then convert that list back into a tuple
```
x = ("apple", "banana", "cherry")
y = list(x)
y[1] = "kiwi"
x = tuple(y)

print(x)
```
- you can add or remove items this way
- you could also add one tuple to another
```
thistuple = ("apple", "banana", "cherry")
y = ("orange",)
thistuple += y

print(thistuple)
```
- you can also use the del keyword with a tuple to delete it completely
```
thistuple = ("apple", "banana", "cherry")
del thistuple
print(thistuple) #this will raise an error because the tuple no longer exists
```
- assigning values to a tuple is called packing it
- unpacking a tuple would be assigning seperate variables to the values within the tuple
```
fruits = ("apple", "banana", "cherry")

(green, yellow, red) = fruits

print(green)
print(yellow)
print(red)
```
- if the number of variables you are using is less than the total number of values in the tuple, then you need to use an asterisk to signify that
```
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")

(green, yellow, *red) = fruits

print(green)
print(yellow)
print(red)
```
- If the asterisk is added to another variable name than the last, Python will assign values to the variable until the number of values left matches the number of variables left.
```
fruits = ("apple", "mango", "papaya", "pineapple", "cherry")

(green, *tropic, red) = fruits

print(green)
print(tropic)
print(red)
```
- looping through a tuple is typically done the same way you would loop through a list
- you can also 'multiply' tuples, essentially adding that tuple to itself based on the number of times it is multiplied
- tuples use much of the same methods that lists do
