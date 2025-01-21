# Python Strings
- use either single or double quotes to mark a string
    - Display using print()
- if you want to use quotes inside a string, they need to be surrounded with either single or double quotes, whichever one doesn’t match the ones encompassing the whole string
```
print("It's alright")
print("He is called 'Johnny'")
print('He is called "Johnny"')
```
- you can also use triple quotes for multiline strings, either 3 single quotes, or 3 double quotes
- Strings are basically arrays, so you can print out their indexes as well
```
a = "Hello, World!"
    print(a[1])

for x in "banana":
    print(x)

a = "Hello, World!"
print(len(a))

txt = "The best things in life are free!"
print("free" in txt)

txt = "The best things in life are free!"
if "free" in txt:
    print("Yes, 'free' is present.")

txt = "The best things in life are free!"
print("expensive" not in txt)

txt = "The best things in life are free!"
if "expensive" not in txt:
    print("No, 'expensive' is NOT present.")
```

## Slicing Strings
```
b = "Hello, World!"
print(b[2:5]) #5 not included
```
- To slice from the start, just include the end character position
```
b = "Hello, World!"
print(b[:5])
```
- You can also slice from some position all the way to the end
```
b = "Hello, World!"
print(b[2:])
```
- You can use negative slicing to remove characters from the end
- Get the characters: From: "o" in "World!" (position -5) To, but not included: "d" in "World!" (position -2):
   ```
   b = "Hello, World!"
   print(b[-5:-2])
   ```
## String modification & String concatenation
- Upper case
```
a = "Hello, World!"
print(a.upper())

a = "Hello, World!"
print(a.lower())
```
- removes whitespace
```
a = " Hello, World! "
print(a.strip()) # returns "Hello, World!" 

a = "Hello, World!"
print(a.replace("H", "J"))

a = "Hello, World!"
print(a.split(",")) # returns ['Hello', ' World!']

a = "Hello"
b = "World"
c = a + b
print(c)

a = "Hello"
b = "World"
c = a + " " + b
print(c)
```

## Formatted Strings & Escape Characters
### Formatted Strings
```
age = 36
txt = f"My name is John, I am {age}"
print(txt)
```
- you can also add modifiers to the formatted strings, using a colon and then some specifier
- Display the price with 2 decimals:
```
price = 59
txt = f"The price is {price:.2f} dollars"
print(txt)
```
- They can also contain python code
```
txt = f"The price is {20 * 59} dollars"
print(txt)
```
### Escape Characters
- used to insert illegal characters into a string
  - `txt = "We are the so-called \"Vikings\" from the north."`
```
\\ - Backslash
\' - Single quote
\" - Double quote
\n - Newline
\t - Horizontal tab
\r - Carriage return
\f - Form feed
\b - Backspace
\ooo - Octal value (e.g., \141 represents 'a')
\xhh - Hexadecimal value (e.g., \x61 represents 'a')
\N{name} - Unicode character by name (e.g., \N{LATIN SMALL LETTER A} represents 'a')
\uhhhh - Unicode character with a 16-bit hex value (e.g., \u00E9 represents 'é')
\Uhhhhhhhh - Unicode character with a 32-bit hex value (e.g., \U0001F600 represents 😀)
\v - Vertical tab
\a - ASCII bell (alert sound)
```
- You can use raw strings to prevent these from being processed
```
print(r"Newline escape: \n")
Outputs: Newline escape: \n
```
## String Methods
### Basic Information
```len("hello")  # Returns the length of the string: 5```

### Case Conversion
```
"Hello".lower()          # Converts to lowercase: 'hello'
"Hello".upper()          # Converts to uppercase: 'HELLO'
"hello world".capitalize()  # Capitalizes the first character: 'Hello world'
"hello world".casefold() # Converts to lowercase (more aggressive): 'hello world'
"hello world".title()    # Capitalizes the first character of each word: 'Hello World'
"Hello".swapcase()       # Swaps the case of all characters: 'hELLO'
```
### Alignment
```
"hello".center(10, '-')  # Centers the string: '--hello---'
"hello".ljust(10, '-')   # Left-aligns the string: 'hello-----'
"hello".rjust(10, '-')   # Right-aligns the string: '-----hello'
```
### Trimming and Stripping
```
"  hello  ".strip()      # Removes leading and trailing characters: 'hello'
"  hello".lstrip()       # Removes leading characters: 'hello'
"hello  ".rstrip()       # Removes trailing characters: 'hello'
```
### Search and Replace
```
"hello".find("l")        # Finds the first occurrence of 'l': 2
"hello".rfind("l")       # Finds the last occurrence of 'l': 3
"hello".index("l")       # Like find() but raises ValueError if not found: 2
"hello".rindex("l")      # Like rfind() but raises ValueError if not found: 3
"hello world".count("o") # Counts occurrences of 'o': 2
"hello world".replace("world", "Python")  # Replaces substrings: 'hello Python'
```
### Splitting and Joining
```
"hello world".split()    # Splits into a list: ['hello', 'world']
"apple,banana,grape".split(',')  # Splits by delimiter: ['apple', 'banana', 'grape']
"hello\nworld".splitlines()  # Splits by line breaks: ['hello', 'world']
",".join(['apple', 'banana', 'grape'])  # Joins a list into a string: 'apple,banana,grape'
```
### Checking String Content
```
"hello".startswith("he") # Checks if it starts with 'he': True
"hello".endswith("lo")   # Checks if it ends with 'lo': True
"hello".isalnum()        # Checks if all characters are alphanumeric: True
"hello".isalpha()        # Checks if all characters are in the alphabet: True
"12345".isdigit()        # Checks if all characters are digits: True
"hello123".isalnum()     # Checks if all characters are alphanumeric: True
"    ".isspace()         # Checks if all characters are whitespace: True
"Hello World".istitle()  # Checks if it's title-cased: True
"HELLO".isupper()        # Checks if all characters are uppercase: True
"hello".islower()        # Checks if all characters are lowercase: True
"12345".isdecimal()      # Checks if all characters are decimal numbers: True
"12345".isnumeric()      # Checks if all characters are numeric: True
"hello".isascii()        # Checks if all characters are ASCII: True
"my_var".isidentifier()  # Checks if it's a valid identifier: True
"hello".isprintable()    # Checks if all characters are printable: True
```
### Formatting Strings
```
"Hello, {}".format("World")  # Formats specified values in a string: 'Hello, World'
"Name: {name}, Age: {age}".format(name="Alice", age=25)  # Named placeholders
"Price: {:.2f}".format(19.999)  # Formats a float to 2 decimal places: 'Price: 20.00'
"hello".zfill(10)            # Pads with zeroes: '000000hello'
```
### Encoding and Decoding
```
"hello".encode("utf-8")      # Encodes the string to bytes: b'hello'
b'hello'.decode("utf-8")     # Decodes bytes back to a string: 'hello'
```
### Translating and Mapping
```
"hello".translate("world")   # Returns a translated string (requires a translation table)
"hello".maketrans("aeiou", "12345")  # Creates a translation table
"hello".expandtabs(4)        # Sets tab size in the string: 'hello'
```
### Partitioning and Splitting
```
"hello world".partition(" ") # Partitions the string: ('hello', ' ', 'world')
"hello world".rpartition(" ")# Partitions from the right: ('hello', ' ', 'world')
"apple,banana,grape".rsplit(",", 1)  # Splits at last occurrence of delimiter: ['apple,banana', 'grape']
```
