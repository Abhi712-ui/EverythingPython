Here is a beginner-friendly Python regex tutorial with short explanations and runnable examples.

# 0) Setup

```python
import re
# Use raw strings for patterns to avoid double escaping
pat = r"\d+\s+\w+"
```

# 1) Mental model

* A regex is a *pattern* the engine tries to match in a string, left to right.
* If a token can match in more than one way, the engine picks the *leftmost* start, then the *longest* it can (greedy) unless you ask for lazy.
* Groups capture substrings while the engine matches.

# 2) Core API (what you actually call)

```python
import re
s = "Name: Ada Lovelace, Age: 36"

re.search(r"Ada", s)            # first match anywhere (Match or None)
re.match(r"Name:", s)           # match only at start
re.fullmatch(r".+", s)          # entire string must match
re.findall(r"\d+", s)           # list of all digit substrings
list(re.finditer(r"\w+", s))    # iterator of Match objects
re.sub(r"\d+", "0", s)          # replace matches
re.split(r"\s*,\s*", "a, b , c")# split by pattern
P = re.compile(r"Age:\s*(\d+)") # precompile for reuse
m = P.search(s)                 # use compiled pattern
```

# 3) Match objects

```python
m = re.search(r"(Ada)\s+(\w+)", "Name: Ada Lovelace")
m.group(0)      # whole match -> 'Ada Lovelace'
m.group(1)      # first capture -> 'Ada'
m.group(2)      # second capture -> 'Lovelace'
m.groups()      # ('Ada', 'Lovelace')
m.start(), m.end(), m.span()  # positions of the whole match
```

# 4) Literals and escaping

* Most characters match themselves. Special characters need escaping inside patterns: `.^$*+?{}[]\|()`
* Prefer raw strings: `r"\."` is a literal dot.

```python
re.search(r"\.", "a.b") is not None   # finds the literal dot
```

# 5) Character classes (match *one* char from a set)

```
[abc]      a or b or c
[a-z]      any lowercase letter
[^abc]     any char except a/b/c
\d \D      digit / not digit
\s \S      whitespace / not whitespace
\w \W      word char / not (letters, digits, underscore; Unicode by default)
```

Tips:

* Put `-` first or last to avoid range: `[-_.]`
* Put `]` first or escape it: `[]A-Z]` or `\]`

```python
re.findall(r"[A-F0-9]{2}", "AF12z")  # ['AF','12']
```

# 6) Anchors and boundaries (zero-width; match *positions*, not chars)

```
^  start of string   $  end of string
\A start of string only    \Z end of string only
\b word boundary           \B not a word boundary
```

```python
re.findall(r"^\w+", "one\ntwo", flags=re.M)   # ['one','two']
re.findall(r"\bcat\b", "concatenate cat cats")# ['cat']
```

# 7) Quantifiers

```
x*        0 or more
x+        1 or more
x?        0 or 1
x{m}      exactly m
x{m,}     at least m
x{m,n}    between m and n (inclusive)
```

Greedy by default; add `?` to make lazy.

```python
re.search(r"<.+>", "<a><b>").group()    # '<a><b>'  greedy
re.search(r"<.+?>", "<a><b>").group()   # '<a>'     lazy
```

# 8) Grouping and captures

```
( ... )              capture group (numbered 1,2,3…)
(?: ... )            non-capturing group
(?P<name> ... )      named group
\1 \2 …              backreference by number
(?P=name)            backreference by name
```

```python
re.sub(r"(\w+),\s*(\w+)", r"\2 \1", "Lovelace, Ada")  # 'Ada Lovelace'
m = re.search(r"(?P<first>\w+)\s+(?P<last>\w+)", "Ada Lovelace")
m.group("first"), m.group("last")  # ('Ada','Lovelace')
```

# 9) Alternation and precedence

```
cat|dog           either
(?:foo|bar)baz    group to limit scope
```

```python
re.findall(r"\b(cat|dog)s?\b", "cats dog doge")  # ['cat','dog']
```

# 10) Lookarounds (advanced but useful; zero-width)

```
(?=...)     positive lookahead
(?!...)     negative lookahead
(?<=...)    positive lookbehind (fixed width)
(?<!...)    negative lookbehind (fixed width)
```

```python
re.findall(r"\w+(?=\.)", "end. mid. no-dot")   # ['end','mid']
re.findall(r"(?<!\$)\b\d+\b", "9 $12 30")      # ['9','30']
```

# 11) Flags (switch behavior)

```python
re.I  # IGNORECASE
re.M  # MULTILINE (^ and $ match at line boundaries)
re.S  # DOTALL (. matches newline)
re.X  # VERBOSE (whitespace and comments allowed in pattern)
re.A  # ASCII character classes and boundaries
```

Inline:

```python
re.search(r"(?i)cat", "CAT")        # ignore case
re.findall(r"(?m)^\w+", "a\nb")     # multiline
```

# 12) Substitution (replace text)

```python
s = "x=7; y=9"
re.sub(r"\d+", "0", s)                          # 'x=0; y=0'

def inc(m): return str(int(m.group(0)) + 1)
re.sub(r"\d+", inc, s)                           # 'x=8; y=10'

# Use \g<1> or \g<name> to avoid ambiguity in repl
re.sub(r"(\w+)-(\d+)", r"\1#\g<2>", "id-42")     # 'id#42'
```

# 13) Splitting

```python
re.split(r"\s*,\s*", "a, b , c")                 # ['a','b','c']
# Keep delimiters by capturing them
re.split(r"(\s*,\s*)", "a, b , c")               # ['a', ', ', 'b', ' , ', 'c']
```

# 14) Verbose patterns (make long patterns readable)

```python
pat = re.compile(r"""
    ^ (?P<user>[A-Za-z_]\w*)   # username
    @
    (?P<host>[A-Za-z0-9.-]+)   # host
$""", re.X)
pat.fullmatch("ada@labs.io").groupdict()         # {'user':'ada','host':'labs.io'}
```

# 15) Building a pattern step by step (worked example)

Goal: parse lines like `"id=42, name=Ada, score=9.5"`

```python
line = "id=42, name=Ada, score=9.5"
# Step 1: literal labels and separators
pat = r"id=\d+,\s*name=\w+,\s*score=\d+(?:\.\d+)?"
re.search(pat, line) is not None                 # True

# Step 2: capture values
pat = r"id=(\d+),\s*name=(\w+),\s*score=(\d+(?:\.\d+)?)"
m = re.search(pat, line)
m.groups()                                       # ('42','Ada','9.5')

# Step 3: named groups, compiled, anchored
P = re.compile(r"""
    ^id=(?P<id>\d+),\s*
    name=(?P<name>\w+),\s*
    score=(?P<score>\d+(?:\.\d+)?)$
""", re.X)
P.fullmatch(line).groupdict()                    # {'id':'42','name':'Ada','score':'9.5'}
```

# 16) Common recipes (with why)

```python
# Collapse whitespace to single spaces
re.sub(r"\s+", " ", "a   b \n c").strip()

# Integer with optional sign (validation)
bool(re.fullmatch(r"[+-]?\d+", "+42"))

# Words including hyphenated terms (tokenization)
re.findall(r"\b(?:\w+(?:-\w+)*)\b", "state-of-the-art v2 alpha")

# Key=value pairs up to semicolon (simple config)
re.findall(r"(\w+)\s*=\s*([^;]+)", "a=1; b = two; c=3")

# Dates like 2025-08-12 (format check)
re.findall(r"\b\d{4}-\d{2}-\d{2}\b", "due 2025-08-12 and 2024-01-01")

# Extract domain from emails
re.findall(r"(?<=@)[A-Za-z0-9.-]+\.[A-Za-z]{2,}", "a@b.io, x@y.z.com")
```

# 17) Debugging and safety

```python
# 1) Catch bad patterns
try:
    re.compile(r"(")
except re.error as e:
    print("bad regex:", e)

# 2) Visualize matches with spans
text = "abc 123 xyz"
for m in re.finditer(r"\w+", text):
    print(m.group(), m.span())

# 3) Anchor when validating
bool(re.fullmatch(r"[a-z_]\w*", "snake_case"))   # True

# 4) Avoid catastrophic backtracking
# Prefer specific classes to nested greedy '.*'
re.search(r"^<[^>]*>$", "<tag>ok</tag>") is None
```

# 18) What stdlib `re` does not support

* Possessive quantifiers (`*+`, `++`) and atomic groups `(?>...)`
* Recursive patterns and subroutines
* Variable-width lookbehind
  (Use third-party `regex` module only if allowed; here we stay with `re`.)

# 19) Practice drills (with hints)

1. **Validate time `HH:MM` (24h).**
   Hint: `(?:[01]\d|2[0-3]):[0-5]\d`
2. **Split CSV by commas but ignore commas inside quotes.**
   Hint: `re.findall(r'"[^"]*"|[^,]+', s)`
3. **Extract hashtag words from text.**
   Hint: `#` followed by `\w+`
4. **Find duplicated consecutive words ignoring case.**
   Hint: `(?i)\b(\w+)\b\s+\1\b`
5. **Validate floating number** with optional sign and decimal part.
   Hint: `^[+-]?(?:\d+(?:\.\d*)?|\.\d+)$`

If you want, I can turn any drill into step-by-step solutions with tests.
