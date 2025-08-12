**Problem: Nested Path Resolver**

1. **Problem statement**
   Write a function `resolve(data, path)` that navigates a nested Python structure using a simple path language and returns the targeted value, or `None` if the path is invalid.

* `data` may contain dicts, lists, tuples, and primitives.
* `path` format:

  * Segments separated by `.` target dict keys.
  * Any segment may have zero or more list/tuple indexers: `[<int>]`.
  * Keys match `[A-Za-z_][A-Za-z0-9_]*` (no dots or brackets inside keys).
  * Indices are base-10 integers. Negative indices are allowed.
* Rules:

  * If a dict key is missing → return `None`.
  * If an index is out of range or the current value is not indexable when an index is requested → return `None`.
  * If the current value is not a dict when a key is requested → return `None`.
  * Do not use `eval`. Standard library only.

Examples of valid paths:

* `user.profile.name`
* `users[0].email`
* `matrix[1][2]`
* `a.b[2].c[0][ -1 ]`  (whitespace inside brackets may occur; ignore it)

2. **Example test cases**

* **Test 1**

  ```python
  data = {
      "user": {
          "profile": {"name": "Ada", "skills": ["py", "algos"]},
          "ids": (10, 20, 30)
      },
      "users": [{"email": "a@x"}, {"email": "b@x"}]
  }
  print(resolve(data, "user.profile.name"))          # -> "Ada"
  print(resolve(data, "user.profile.skills[1]"))     # -> "algos"
  print(resolve(data, "user.ids[-1]"))               # -> 30
  ```
* **Test 2**

  ```python
  data = {"matrix": [[1,2,3],[4,5,6],[7,8,9]]}
  print(resolve(data, "matrix[1][2]"))   # -> 6
  print(resolve(data, "matrix[3][0]"))   # -> None   (index out of range)
  print(resolve(data, "matrix.rows"))    # -> None   (not a dict at that step)
  ```
* **Test 3**

  ```python
  data = {"a":{"b":[{"c":1},{"c":2},{"c":[7,8,9]}]}}
  print(resolve(data, "a.b[2].c[0]"))      # -> 7
  print(resolve(data, "a.b[ 2 ].c[ 5 ]"))  # -> None
  print(resolve(data, "a.b[1].d"))         # -> None
  ```

3. **Hint**
   Parse each dot-separated segment, then scan it left→right. First read the key (letters, digits, underscores starting with a letter or underscore). Then while you see `[ ... ]`, strip spaces inside, parse the integer, and index into the current value. Validate types at every step.

4. **Estimated difficulty**
   3/5
