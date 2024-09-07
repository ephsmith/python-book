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
Name rules apply to:

- all source code
- the names of Python files
- the names of any directories used in a Python source tree.

When Python modules are imported, they become names that are available to our code.  Given this, it makes sense that file and directory names in Python source trees must also follow naming rules.

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


## Other Python Naming Conventions

### Names with Leading Underscores
Names with leading underscores are considered by **convention** to be *private* and only 
to be referenced or called from the module in which they are defined.  
This is not enforced by Python itself, but is often enforced by code checkers in 
modern CI/CD pipelines. Code completion features in many IDEs and the Python shell 
itself do not auto-complete names that begin with an underscore.

```py title="leading_underscores.py"
def _convert_to_dollar_str(float_value):
    '''_convert_to_dollar_str is a private function used only in the 
    module it is defined in.'''
    return f'$ {float_value:0.2f}'
```

Third-party developers often use such names to discourage end users of the library 
from referencing variables or calling functions that were not meant to be called 
directly. Calling `dir()`. 

### Names with Trailing Underscores
It is common practice to use a trailing underscore on a name that would otherwise 
collide with a built-in or previously defined variable. Consider the following Python 
code block which collects values into a "sum" variable. If the code used the name 
`sum` it would overwrite the built-in `sum()` function which would then be unreachable 
by subsequent code.

```py title="trailing_underscores.py"
matching_product_counts = [10, 20, 30, 40]
sum_ = 0

for count in matching_product_counts:
    sum_ += count  #  (1)! 
    
print(f'Summed in loop: sum_ = {sum_}')
    
# The loop is unnecessary thanks to Python's sum()
sum_ = sum(matching_product_counts)  #  (2)!
print(f'Summed using built-in sum(): sum_ = {sum_}')
```

1. The trailing underscore differentiates the local "sum" variable `sum_` from the 
   built-in Python function `sum()`
2. Because `sum_` does not overwrite `sum()` the latter is still available to use as a 
   function.

!!! tip
    When using a name that is identical to a built-in function, use a trailing 
    underscore to differentiate it from existing name. Use this technique sparingly 
    though and consider using a more meaningful variable name.   


!!! warning
    If you do happen to (or need to) overwrite a built-in name, you can reclaim access 
    to it by removing the name assignment using the `del` keyword. Example: If you 
    overwrite `sum()` by assigning `sum = 5`, running `del sum` will reclaim the 
    reference to the built-in `sum()`. Note that this only works with built-ins.  

### UPPERCASE Names
It is convention to use UPPER_CASE (snake case) for names to which constants are 
defined.  For example, the number of minutes in a day never changes in the real world 
and is therefore a constant if used in a program. 

Example:

```py
MINUTES_PER_DAY = 1440

minutes_so_far = 14_440_000

days_so_far = minutes_so_far / MINUTES_PER_DAY
```















