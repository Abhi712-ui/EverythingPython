# Core API

```python
import re

re.search(pat, s)        # first match anywhere -> Match or None
re.match(pat, s)         # match at start only -> Match or None
re.fullmatch(pat, s)     # entire string must match -> Match or None
re.findall(pat, s)       # list of captured strings or tuples
re.finditer(pat, s)      # iterator of Match objects
re.sub(pat, repl, s, count=0)      # replace; repl str or func
re.subn(pat, repl, s)              # like sub, also returns count
re.split(pat, s, maxsplit=0)       # split by pattern
re.compile(pat, flags=0)           # precompile -> Pattern
re.escape(s)            # escape literal text for use in a pattern
```

# Match object

```python
m.group(0)          # whole match
m.group(1)          # capture 1
m.groups()          # tuple of all captures
m.groupdict()       # dict of named captures
m.start(i), m.end(i), m.span(i)   # positions
```

# Flags

```python
re.I or re.IGNORECASE
re.M or re.MULTILINE       # ^ and $ match at line boundaries
re.S or re.DOTALL          # . matches newline
re.X or re.VERBOSE         # whitespace/comments in pattern
re.A or re.ASCII           # \w, \b, etc. limited to ASCII
```

Inline: `(?imxs)` or scoped `(?i:...)`.

# Atoms and classes

```
.           any char except \n (use DOTALL to include \n)
[abc]       a or b or c
[a-z]       range
[^abc]      not a/b/c
\d \D       digit / not digit
\s \S       whitespace / not
\w \W       word char / not   (affected by ASCII flag)
```

# Anchors and boundaries

```
^           start of string (or line with MULTILINE)
$           end of string (or line with MULTILINE)
\A          start of string only
\Z          end of string only
\b          word boundary
\B          not a word boundary
```

# Quantifiers

```
x*          0 or more
x+          1 or more
x?          0 or 1
x{m}        exactly m
x{m,}       at least m
x{m,n}      between m and n
```

Greedy by default. Add `?` to make lazy: `*? +? ?? {m,n}?`.

# Grouping and captures

```
(...)               capture group
(?:...)             non-capturing group
(?P<name>...)       named capture
(?P=name)           backref by name
\1 \2 ...           backref by number
```

# Alternation and precedence

```
A|B         A or B
()          groups control alternation scope
```

# Lookarounds (zero-width)

```
(?=...)     positive lookahead
(?!...)     negative lookahead
(?<=...)    positive lookbehind   # fixed-width only
(?<!...)    negative lookbehind   # fixed-width only
```

# Substitution

```python
re.sub(r"(\w+), (\w+)", r"\2 \1", s)     # use \1 or \g<1>
re.sub(r"(\d+)", lambda m: str(int(m.group(1))+1), s)
```

Use `\g<name>` or `\g<1>` to avoid escape ambiguity.

# Verbose mode (readable patterns)

```python
pat = re.compile(r"""
    ^ (?P<user>[A-Za-z_]\w*)   # username
    @
    (?P<host>[A-Za-z0-9.-]+)   # host
$""", re.X)
```

# Raw strings

Use raw literals for patterns to avoid double escaping.

```python
r"\d+\s+\w+"     # good
"\\d+\\s+\\w+"   # noisy
```

# Common mini-recipes

```python
# 1) Collapse whitespace
re.sub(r"\s+", " ", s).strip()

# 2) Validate simple integer (optional sign)
bool(re.fullmatch(r"[+-]?\d+", s))

# 3) Split on commas ignoring surrounding spaces
re.split(r"\s*,\s*", s)

# 4) Extract all words
re.findall(r"\b\w+\b", s)

# 5) Find duplicated consecutive words (case-insensitive)
re.findall(r"(?i)\b(\w+)\b\s+\1\b", s)

# 6) Simple IPv4 (not range-validated)
re.findall(r"\b(?:\d{1,3}\.){3}\d{1,3}\b", s)

# 7) Snake_case identifiers
bool(re.fullmatch(r"[a-z_]\w*", s))

# 8) Numbers with optional decimals
re.findall(r"[+-]?(?:\d+(?:\.\d*)?|\.\d+)", s)

# 9) Strip HTML tags (naive)
re.sub(r"<[^>]*>", "", html)

# 10) Grab text inside balanced quotes (no escapes)
re.findall(r'"([^"\n]*)"', s)
```

# Character class tips

* Put `-` first or last to avoid range: `[-._]`.
* Escape `]` as `\]` or place first: `[]A-Z]`.
* No set subtraction or intersections in stdlib `re`.

# Performance notes

* Prefer `re.compile` for repeated use.
* Narrow patterns. Anchor with `^` and `$` when possible.
* Avoid catastrophic backtracking: keep nested `.*` or `.+` in check, use lazy quantifiers or explicit classes.

# Unsupported in stdlib `re`

* Possessive quantifiers (`++`, `*+`) and atomic groups (`(?>...)`).
* Recursion and subroutines.
  (Use third-party `regex` module if you need these.)

# Quick demo

```python
import re

text = "Name: Ada Lovelace, Age: 36"
m = re.search(r"Name:\s*(?P<first>\w+)\s+(?P<last>\w+),\s*Age:\s*(\d+)", text)
if m:
    print(m.group("first"), m.group("last"), m.group(3))  # Ada Lovelace 36
```

Ask for expansions on any section or a targeted set of practice exercises.
