# Python Dictionaries
```
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
```
 - Items in a dictionary are key value pairs
 - they are ordered, changable, and do not allow for duplicates
```
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
print(thisdict["brand"])
```
 - When we say that dictionaries are ordered, it means that the items have a defined order, and that order will not change.
 - Unordered means that the items do not have a defined order, you cannot refer to an item by using an index.
 - dictionaries cannot have two items with the same key
 - values in dictionary key value pairs can be of any data type
```
thisdict = dict(name = "John", age = 36, country = "Norway")
print(thisdict)
```
## Accessing Dictionary Items in Python

### 1. Accessing Values by Key
 - Use square brackets to access the value associated with a specific key.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
value = my_dict["name"]  # Returns "Alice"
```
### 2. Using get() Method
 - Use get() to safely access a value without raising a KeyError if the key does not exist.
```
value = my_dict.get("age")  # Returns 25
value = my_dict.get("country", "Not Found")  # Returns "Not Found" (default value)
```
### 3. Check for Key Existence
 - Use the "in" operator to check if a key exists in the dictionary.
```
if "name" in my_dict:
    print("Key exists")  # Outputs: Key exists
```
### 4. Accessing All Keys
 - Use the keys() method to get a view of all keys in the dictionary.
```
keys = my_dict.keys()  # Returns dict_keys(['name', 'age', 'city'])
```
### 5. Accessing All Values
 - Use the values() method to get a view of all values in the dictionary.
```
values = my_dict.values()  # Returns dict_values(['Alice', 25, 'New York'])
```
### 6. Accessing All Key-Value Pairs
 - Use the items() method to get a view of all key-value pairs as tuples.
```
items = my_dict.items()  # Returns dict_items([('name', 'Alice'), ('age', 25), ('city', 'New York')])
```
### 7. Iterating Over a Dictionary
 - Use a for loop to iterate over keys, values, or key-value pairs.
```
# Example: Iterating over keys
for key in my_dict:
    print(key)  # Outputs: name, age, city

# Example: Iterating over values
for value in my_dict.values():
    print(value)  # Outputs: Alice, 25, New York

# Example: Iterating over key-value pairs
for key, value in my_dict.items():
    print(key, value)  # Outputs: name Alice, age 25, city New York
```
## Changing Dictionary Items in Python

### 1. Updating a Value by Key
 - Use square brackets to update the value associated with a specific key.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
my_dict["age"] = 26  # Updates the "age" key to 26
print(my_dict)  # {'name': 'Alice', 'age': 26, 'city': 'New York'}
```
### 2. Adding a New Key-Value Pair
 - Assign a value to a new key to add it to the dictionary.
```
my_dict["country"] = "USA"  # Adds a new key "country" with value "USA"
print(my_dict)  # {'name': 'Alice', 'age': 26, 'city': 'New York', 'country': 'USA'}
```
### 3. Using the update() Method
 - Updates the dictionary with key-value pairs from another dictionary or iterable.
```
my_dict.update({"age": 27, "hobby": "reading"})  # Updates "age" and adds "hobby"
print(my_dict)  # {'name': 'Alice', 'age': 27, 'city': 'New York', 'country': 'USA', 'hobby': 'reading'}
```
### 4. Conditional Updates
 - Check if a key exists before updating or adding.
```
if "city" in my_dict:
    my_dict["city"] = "Los Angeles"  # Updates "city" to "Los Angeles"
print(my_dict)  # {'name': 'Alice', 'age': 27, 'city': 'Los Angeles', 'country': 'USA', 'hobby': 'reading'}
```
### 5. Using setdefault()
 - Updates a dictionary only if the key does not already exist.
```
my_dict.setdefault("profession", "Engineer")  # Adds "profession" with value "Engineer"
my_dict.setdefault("city", "San Francisco")  # Does nothing since "city" already exists
print(my_dict)  # {'name': 'Alice', 'age': 27, 'city': 'Los Angeles', 'country': 'USA', 'hobby': 'reading', 'profession': 'Engineer'}
```
## Removing Dictionary Items in Python

### 1. Using pop()
 - Removes the specified key and returns its value. Raises KeyError if the key is not found.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
removed_value = my_dict.pop("age")  # Removes "age" and returns 25
print(my_dict)  # {'name': 'Alice', 'city': 'New York'}
print(removed_value)  # 25
```
### 2. Using pop() with Default Value
 - Avoids KeyError by providing a default value if the key does not exist.
```
removed_value = my_dict.pop("country", "Not Found")  # Key doesn't exist, returns "Not Found"
print(removed_value)  # Not Found
```
### 3. Using popitem()
- Removes and returns the last inserted key-value pair as a tuple.
```
# In Python 3.7+, dictionaries maintain insertion order.
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
removed_item = my_dict.popitem()  # Removes and returns ('city', 'New York')
print(my_dict)  # {'name': 'Alice', 'age': 25'}
print(removed_item)  # ('city', 'New York')
```
### 4. Using del Statement
 - Removes a key-value pair by key. Raises KeyError if the key does not exist.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
del my_dict["city"]  # Removes the key "city"
print(my_dict)  # {'name': 'Alice', 'age': 25'}
```
### 5. Using del to Delete the Entire Dictionary
 - Deletes the entire dictionary from memory.
```
del my_dict  # The variable my_dict is no longer defined.
```
### 6. Using clear()
 - Removes all items from the dictionary, leaving it empty.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
my_dict.clear()  # Clears all items
print(my_dict)  # {}
```
### 7. Conditional Removal
 - Check if a key exists before removing it to avoid errors.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
if "age" in my_dict:
    del my_dict["age"]  # Removes "age" if it exists
print(my_dict)  # {'name': 'Alice', 'city': 'New York'}
```
## Looping Through a Dictionary in Python

### 1. Looping Through Keys
 - By default, iterating over a dictionary loops through its keys.
```
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
for key in my_dict:
    print(key)  # Outputs: name, age, city
```
### 2. Looping Through Values
 - Use the `values()` method to loop through the dictionary's values.
```
for value in my_dict.values():
    print(value)  # Outputs: Alice, 25, New York
```
### 3. Looping Through Key-Value Pairs
 - Use the items() method to loop through key-value pairs as tuples.
```
for key, value in my_dict.items():
    print(key, value)
    # Outputs:
    # name Alice
    # age 25
    # city New York
```
### 4. Looping Through Keys and Accessing Values
 - Access the value using the key inside the loop.
```
for key in my_dict:
    print(key, my_dict[key])
    # Outputs:
    # name Alice
    # age 25
    # city New York
```
### 5. Using Enumerate with Keys
 - Use enumerate() to get an index while iterating over keys.
```
for index, key in enumerate(my_dict):
    print(index, key)
    # Outputs:
    # 0 name
    # 1 age
    # 2 city
```
### 6. Using Enumerate with Key-Value Pairs
 - Combine enumerate() with items() to get an index along with keys and values.
```
for index, (key, value) in enumerate(my_dict.items()):
    print(index, key, value)
    # Outputs:
    # 0 name Alice
    # 1 age 25
    # 2 city New York
```
### 7. Looping Through Keys in Sorted Order
 - Use sorted() to loop through the keys in alphabetical order.
```
for key in sorted(my_dict):
    print(key, my_dict[key])
    # Outputs:
    # age 25
    # city New York
    # name Alice
```
### 8. Looping Through Values in Sorted Order
 - Use sorted() to loop through values in ascending order.
```
for value in sorted(my_dict.values()):
    print(value)
    # Outputs:
    # 25
    # Alice
    # New York
```
### 9. Looping Through Keys, Filtering by Condition
 - Apply a condition to filter keys during iteration.
```
for key in my_dict:
    if "a" in key:
        print(key, my_dict[key])
        # Outputs:
        # name Alice
        # age 25
```
## Copying Dictionaries in Python

### 1. Using the `copy()` Method
- Creates a shallow copy of the dictionary.
- Changes to the original dictionary won't affect the copy (unless the values are mutable objects like lists).
```
original_dict = {"name": "Alice", "age": 25}
copied_dict = original_dict.copy()
print(copied_dict)  # Output: {'name': 'Alice', 'age': 25'}
```
### 2. Using the `dict()` Constructor
 - Another way to create a shallow copy of a dictionary.
```
original_dict = {"name": "Alice", "age": 25}
copied_dict = dict(original_dict)
print(copied_dict)  # Output: {'name': 'Alice', 'age': 25'}
```
### 3. Using Dictionary Comprehension
 - Creates a new dictionary by iterating through the original dictionary.
```
original_dict = {"name": "Alice", "age": 25}
copied_dict = {key: value for key, value in original_dict.items()}
print(copied_dict)  # Output: {'name': 'Alice', 'age': 25'}
```
### 4. Using the `deepcopy()` Method from `copy` Module
 - Creates a deep copy of the dictionary, meaning nested dictionaries or other mutable objects are also copied.
 - Changes to the nested objects in the original dictionary won’t affect the deep copy.
```
import copy
original_dict = {"name": "Alice", "details": {"age": 25, "city": "New York"}}
deep_copied_dict = copy.deepcopy(original_dict)
print(deep_copied_dict)  # Output: {'name': 'Alice', 'details': {'age': 25, 'city': 'New York'}}
```
### 5. Using Shallow Copy with Nested Dictionaries (Caution)
 - If a dictionary contains mutable objects (e.g., lists or other dictionaries), a shallow copy will share references to those objects.
 - Changes to the mutable objects will affect both dictionaries.
```
original_dict = {"name": "Alice", "details": {"age": 25, "city": "New York"}}
shallow_copy = original_dict.copy()
shallow_copy["details"]["age"] = 30  # Changes the original dictionary as well!
print(original_dict)  # Output: {'name': 'Alice', 'details': {'age': 30, 'city': 'New York'}}
```
### 6. Comparison of Methods
 | **Method**       | **Type**    | **Copies Nested Objects?** | **Best Use Case**                     |
 |-------------------|-------------|----------------------------|----------------------------------------|
 | `copy()`         | Shallow     | No                         | Simple, flat dictionaries.            |
 | `dict()`         | Shallow     | No                         | Alternative to `copy()`.              |
 | Dictionary Comp. | Shallow     | No                         | Custom filtering or transformations.  |
 | `deepcopy()`     | Deep        | Yes                        | Complex dictionaries with nested data.|

### Key Points:
 - Use `copy()` or `dict()` for shallow copies when your dictionary does not contain nested structures.
 - Use `copy.deepcopy()` for deep copies to handle nested dictionaries or mutable objects safely.

## Working with Nested Dictionaries in Python

### 1. Accessing Items in a Nested Dictionary
 - Use multiple keys to access items in a nested dictionary.
```
nested_dict = {
    "person": {
        "name": "Alice",
        "age": 25,
        "address": {
            "city": "New York",
            "zip": "10001"
        }
    }
}
```
#### Accessing the city
```
city = nested_dict["person"]["address"]["city"]
print(city)  # Output: New York
```
### 2. Modifying Items in a Nested Dictionary
 - Modify values by specifying the full path of keys.
```
nested_dict["person"]["address"]["city"] = "Los Angeles"
print(nested_dict["person"]["address"]["city"])  # Output: Los Angeles
```
### 3. Adding Items to a Nested Dictionary
 - Add new key-value pairs at any level.
```
nested_dict["person"]["address"]["state"] = "California"
print(nested_dict["person"]["address"])
#Output: `{'city': 'Los Angeles', 'zip': '10001', 'state': 'California'}`
```
### 4. Removing Items from a Nested Dictionary
 - Use the `del` statement or `pop()` to remove items.
```
# Using `del`
del nested_dict["person"]["address"]["zip"]
print(nested_dict["person"]["address"])  # Output: {'city': 'Los Angeles', 'state': 'California'}
```
#### Using `pop()`
removed_value = nested_dict["person"]["address"].pop("state")
print(removed_value)  # Output: California
print(nested_dict["person"]["address"])  # Output: {'city': 'Los Angeles'}

### 5. Looping Through Nested Dictionaries
 - Use nested loops or recursive functions to iterate through all items.
```
# Looping through top-level keys
for key, value in nested_dict["person"].items():
    print(key, value)
# Output:
# name Alice
# age 25
# address {'city': 'Los Angeles'}

# Looping through all levels using recursion
def print_nested(d):
    for key, value in d.items():
        if isinstance(value, dict):
            print(f"{key}:")
            print_nested(value)
        else:
            print(f"{key}: {value}")

print_nested(nested_dict)
# Output:
# name: Alice
# age: 25
# address:
#   city: Los Angeles
```
### 6. Copying Nested Dictionaries
 - Use `copy.deepcopy()` for deep copies to avoid shared references.
```
import copy
nested_copy = copy.deepcopy(nested_dict)
nested_copy["person"]["name"] = "Bob"
print(nested_dict["person"]["name"])  # Output: Alice (original remains unchanged)
```
### 7. Updating Nested Dictionaries
 - Use the `update()` method for shallow updates or custom functions for deep updates.
```
nested_dict["person"]["address"].update({"zip": "90001", "state": "California"})
print(nested_dict["person"]["address"])
# Output: {'city': 'Los Angeles', 'zip': '90001', 'state': 'California'}
```
## Python Dictionary Methods

### 1. `clear()`
 - Removes all items from the dictionary.
```
my_dict = {"name": "Alice", "age": 25}
my_dict.clear()
print(my_dict)  # Output: {}
```
### 2. `copy()`
 - Returns a shallow copy of the dictionary.
```
my_dict = {"name": "Alice", "age": 25}
copied_dict = my_dict.copy()
print(copied_dict)  # Output: {'name': 'Alice', 'age': 25'}
```
### 3. `fromkeys()`
 - Creates a dictionary with specified keys and a default value.
```
keys = ["a", "b", "c"]
default_value = 0
new_dict = dict.fromkeys(keys, default_value)
print(new_dict)  # Output: {'a': 0, 'b': 0, 'c': 0}
```
### 4. `get()`
 - Returns the value for a specified key, or a default value if the key is not found.
```
my_dict = {"name": "Alice", "age": 25}
print(my_dict.get("name"))  # Output: Alice
print(my_dict.get("city", "Not Found"))  # Output: Not Found
```
### 5. `items()`
 - Returns a view object containing key-value pairs as tuples.
```
my_dict = {"name": "Alice", "age": 25}
print(my_dict.items())  # Output: dict_items([('name', 'Alice'), ('age', 25)])
```
### 6. `keys()`
 - Returns a view object containing the dictionary's keys.
```
my_dict = {"name": "Alice", "age": 25}
print(my_dict.keys())  # Output: dict_keys(['name', 'age'])
```
### 7. `pop()`
 - Removes the specified key and returns its value. Raises KeyError if the key is not found.
```
my_dict = {"name": "Alice", "age": 25}
age = my_dict.pop("age")
print(age)  # Output: 25
print(my_dict)  # Output: {'name': 'Alice'}
```
### 8. `popitem()`
 - Removes and returns the last inserted key-value pair as a tuple. Raises KeyError if the dictionary is empty.
```
my_dict = {"name": "Alice", "age": 25}
last_item = my_dict.popitem()
print(last_item)  # Output: ('age', 25)
print(my_dict)  # Output: {'name': 'Alice'}
```
### 9. `setdefault()`
 - Returns the value of a specified key. If the key does not exist, it inserts the key with the specified default value.
```
my_dict = {"name": "Alice"}
value = my_dict.setdefault("age", 25)
print(value)  # Output: 25
print(my_dict)  # Output: {'name': 'Alice', 'age': 25}
```
### 10. `update()`
 - Updates the dictionary with key-value pairs from another dictionary or iterable.
```
my_dict = {"name": "Alice"}
my_dict.update({"age": 25, "city": "New York"})
print(my_dict)  # Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```
### 11. `values()`
 - Returns a view object containing the dictionary's values.
```
my_dict = {"name": "Alice", "age": 25}
print(my_dict.values())  # Output: dict_values(['Alice', 25])
```
### 12. `del`
 - Removes a specified key-value pair using the `del` statement.
```
my_dict = {"name": "Alice", "age": 25}
del my_dict["age"]
print(my_dict)  # Output: {'name': 'Alice'}
```
