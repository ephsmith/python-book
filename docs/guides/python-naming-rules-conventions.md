## Rules for Names in Python
The rules for names in Python are simple, yet important. One common
pitfall is forgetting that names are case sensitive in Python. This
means that `height` and `Height` are different names in Python.

- A variable name must start with a letter or the underscore character
  (`_`)
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and
  underscores (`A-Z`, `a-z`, `0-9`, and `_` ).
- Variable names are case-sensitive (`age`, `Age` and `AGE` are three
  different variables)

## Where do name rules apply?
Name rules apply to all source code and the names of Python files and any directories 
used in a Python source tree. When Python modules are imported, they become names that 
are available to our code.  Given this, it makes sense that file and directory names 
in Python source trees must also follow naming rules.

## PEP8 Conventions for Names
Generally speaking, a convention is a widely accepted way of doing things. The same is 
true for naming conventions. These are *not* language rules. While they can be broken 
without affecting program operation, it is generally frowned upon by development teams 
and the community at large. PEP8 defines some conventions (guidelines) for naming. 
These are part of the PEP8 style guide. Examples are listed below.

| Object Category   |  Name Example     | Style Name    |
|-------------------|-------------------|---------------|
| variable names    | `births_per_capita` | snake_case    |
| function names    | `get_username()`    | snake_case    |
| class names       | `UserProperties()`  | CamelCase     |
| module names      | `process_files.py`  | snake_case    |

