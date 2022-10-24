## Introduction
In software programming data types are an important concept. Python programs can 
operate on a variety of types of data.  Different types are handled differently in a 
Python program so it is important to understand the basic types that Python provides.

Python data types fall into two categories: 

- simple or atomic data types: can not be decomposed into a collection of another type
- non-atomic data types: are composed of other types

Here each of the following types will be covered along with elementary operations that 
can be performed on them. Later chapters provide more detailed coverage and examples 
for each type.

## Built-in Atomic Types
Python has the following bult-in atomic types:

- Text type: `str`
- Numeric types: `int`, `float`, `complex`
- Boolean type: `bool`
- None Type: `NoneType`

## Built-in Non-Atomic Types

- Sequences: `list`, `tuple`, `range`
- Mappings: `dict`
- Sets: `set`, `frozenset`
- Binary Types: `bytes`, `bytearray`

## Determining a Variable's Type
There are two common methods to determine the type of a variable.  When using the 
interactive Python shell, the `type()` function is the quickest way to check the type 
of a variable or a value returned from a function/operation.

```python
>>> type('hello')
str
>>> type(100)
int
>>> type(100.100)
float
>>> type(True)
bool
```

If the type check is being performed in a program, it is often preferable to use the 
`isinstance()` function. This function operates a bit differently, but has the added 
benefit of returning a `bool` (`True` or `False`) value which can be used to 
programmatically determine how to handle the data in a program. 

```python
>>> message = 'Assignment Complete!'
>>> count = 200
>>> length = 10.5
>>> isinstance(message, str)
True
>>> isinstance(count, int)
True
>>> isinstance(length, float)
True
```

Type checks such as these are useful when we want to account for problems that occur 
at runtime or when we simply want to operate on differnt types in different ways. 

To summarize, use `type()` for interactive variable type checks and use `isinstance()` 
when checking the type in a program.

## Text Type: `str`
Many other languages have multiple text types. In C++, for example, strings are 
non-atomic compositions of an atomic character type. Python differs in this regard. 
*The only text type in Python is the `str` type.* 

!!! note
    The `bytes` type is commonly used to store text that is transmitted over a 
    communication interface, but this is not technically a text type. In fact, `bytes` 
    objects must be decoded to convert them to strings.

### Literals and Variables
A **literal** is an actual value of a certain type that is included in our code. 
String literals are entered as characters, surrounded by (delimited with) single or 
double quotes.

The following simple program includes some string literal examples.

```python title="string_examples.py"
country_code = 'CA' #  (1)!
product_code = "EZ123"  # (2)!
print(country_code, product_code)
```

1. `CA` is a string literal.
2. `EZ123` is also a string literal.

When we run this program, the following is printed to the screen.

```python
CA EZ123
```

To create a string variable, assign a string literal to a name using the assignment 
operator `=`.  In the program above, `country_code` and `product_code` are both string 
variables because they have `str` types assigned to them. We can verify this

1. save the code above to a Python module named `string_examples.py` and run it using 
   IDLE. 
2. Type the following lines of code at the prompt in the Python shell. 

```py
>>> type(country_code)
str
>>> isinstance(product_code, str)
True
```

### The `str()` Function
The `str()` function can be used to:

- create an empty string: `str()` with no arguments yields `''`. 
- convert a compatible type to a string. Example: `str(5)` yields `"5"`

### Basic Operations
Some basic string operations include:

- concatenation
- repetition

The following code sample demonstrates these to common string operations.

```py title="string_examples.py"
>>> first_name = "Isaiah"
>>> last_name = "Thomas"
>>> full_name = first_name + " " + last_name  #  (1)!
>>> border = "#" * 20  # (2)!
>>> print(border)
>>> print(full_name)
```

1. **Concatenation**: The `+` operator is used to concatenate strings.
2. **Repetition**: The `*` operator is used for string repetition.

Strings can be concatenated using the `+` operator. Note that this is 
both operands must be `str` types. 

The `*` is an interesting case where mixed types are allowed as operands. Repetition 
expressions are only allowed with `str` and `int` types. Attempting to use a `float` 
will result in an error.

This completes a basic introduction to string types. More detail will be provided in 
later chapters.

## Numeric Types
Python has three built-in atomic numeric types.  This text focuses on `int` and 
`float` types. 

|Type     | Description      | Literal Examples|
|---------|------------------|---------|
|`int`    | Integer type     |`1`, `-200`, `7_654_321`|
|`float`  | Float type       |`1.11`, `-200.0`, `1_234_567.8`|
|`complex`| Complex type     |`1 + 1j`, `2.2 + 5j`|

###  Literals and Variables
Just as with `str` types, we need to be aware of how to enter literal values for 
numeric types. The table above provides examples literals for each numeric type. 
Creating a variable from any of these types is accomplished the same way as with 
strings.  We use the assignment operator `=`.  The following code assigns some numeric 
literals to names.  When you run this code in IDLE, you can run type checks on the 
variables using the Python shell.

```py title="numeric_examples.py"
product_count = 1000
product_weight = 22.3
```

### Special Literal Formatting
Python numeric types allow the use of underscores (`_`) as thousands separators.  This 
can be helpful with large values with many repeated digits. Python `float` types allow 
the use of standard exponential notation for representing very large and very small 
numbers.  The following examples demonstrate these helpful formats.

```py
a_very_large_int = 1_000_000_000_000
a very_large_float = 1_000.000_123_123
one_thousand = 1e3 
one_thousanth = 1E-3
```

### The `int()` Function
This function can be used to:

- create a zero-valued `int`. Example: `int()` yields `0`.
- convert a compatible type to an `int` type. Example: `int("10")` yields an `int` `10`.

The following example demonstrates a basic `int` conversion. Note that `age_in_months` 
could be defined initially as an `int`. It is defined first as a string here for 
demonstration purposes. 

```py title="numeric_examples.py"
MONTHS_PER_YEAR = 12
name = "Phoenix"
age_in_months = "12"

# convert age_in_months to a int
age_in_months = int(age_in_months)
age_in_years = age_in_months / MONTHS_PER_YEAR
print(f'{name} is {age_in_months} months (or {age_in_years} years) old!')
```

### The `float()` function
This function is used to:

- create a zero-valued `float` type. Example: `float()` yields `0.0` (a `float` type).
- convert a compatible type to `float`. Example: `float("1.234")` yields `1.234`. 

### Type Checks
The Python shell session excerpt below demonstrates type checks on numeric types.  The 
pattern is the same regardless of the type.  We just supply the correct arguments to 
the `type()` and `isinstance()` functions.

```py
>>> type(product_count)
int
>>> type(product_weight)
float
>>> isinstance(product_count, int)
True
>>> isinstance(product_weight, float)
True
```

We will explore methods and operations with numeric types in the coming chapters. For 
now, we continue our survey of basic Python types with the Boolean type `bool`.

### Basic Operations
Basic operations for numeric types were covered in the [Use Python as a Calculator](02-setting-up-python.md#use-python-as-a-calculator)
section. Operations on numeric types can have mixed numeric operands.  For example we 
can add an `int` to a `float`. In such cases, the result type will be that of the 
`type` with higher precision--`float` in the case of an `int`-`float` operation.

## Boolean Type: `bool`
The boolean type `bool` is a special type in Python that is used for representing one 
of two values: `True` and `False`. These are a special type in Python because they can 
also be used in any expression where an `int` type is allowed. This is because the 
`bool` type is implemented as a subclass of `int` in Python. *We know how to test this*.

```py
>>> isinstance(True, bool)
True
>>> isinstance(False, int)
True
```

### Literals and Variables
The previous example demonstrated a few things.  We can see `bool` literals `True` and 
`False` in the `isinstance()` checks. We also see that `bool` types are both `int` and 
`bool`.  When a `bool` type is interpreted as an `int`, `True` is `1` and `False` is 
`0`.  We can see this in action if we introduce a new function--`int()`.  

```pycon
>>> int(True)
1
>>> int(False)
0
```

Values of type `bool` can be assigned to a name just like any other type in Python. 

```pycon
>>> product_in_stock = False
>>> product_is_back_ordered = True 
```

We will see `bool` types again when we cover decision making in Python. 


### The `bool()` Function
This function is used to:

- create a False valued `bool` type. Example: `bool()` yields `False`.
- convert a compatible type to a `bool` type. `bool(1)` yields `True`.
- interpret a Python object as a boolean (True or False)

The third bullet above requires a bit more explanation.  In general, Python considers 
any 0 value to be False.  Non-numeric types are interpreted differently.  A 
zero-valued string, for example, has no characters. For built-in types, the value 
returned by the function associated with the type is considered as False.

The following list has some example of boolean interpretation of non-numeric types. 

- empty strings: `False`
- empty lists or tuples: `False`
- non-empty string, list, or tuple: `True` 

## `NoneType` Type
This is a special type in Python. More accurately, there is only one instance of this type
stored in memory in a Python program as `None`.  It is used to represent the absence 
of a value. This type is used as:

- default arguments in functions
- to check the return (or absence of a return) value from a function
- an explicit value returned form a function to signal information to the caller

!!! caution
    Always use the `is` keyword when making comparisons to `None`.  Example `if name is 
    None...`.  

## Sequence Types
A Python sequence is an ordered collection of items which can be accessed by index 
number. The length of any sequence can be determined by passing it to the `len()` 
function which is introduced in this section.

In addition to lists and tuples, string and bytes types are also sequences. This 
section focuses on:

- list type: `list`
- tuple type: `tuple`

### List Types
A Python list is an ordered collection of Python objects.  List can hold any 
type--even other lists.  To define a list using a literal, surround a comma-separated 
list of object with square brackets: `[ ]`. 

```py title="list_examples.py"
nums = [1, 2, 3]  # (1)!
print(type(nums)) # (2)!
print(nums)       # (3)!
len(nums)         # (4)!
```

1. The `list` literal here is a sequence of numbers, separated by commas and 
   surrounded by a pair of square brackets.
2. When inspecting type from a Python module, we need to use the `print()` function to 
   actually see it in the shell output.
3. We can use `print()` on lists to see a literal representation of the variable.
4. Pass any sequence to the `len()` function to get the number of items stored. 

```pycon
>>>
list
[1, 2, 3]
4
```

#### The list() Function
As with other types, the `list()` function, called with no arguments, returns an 
*empty* list. When called with a compatible argument, the input argument is converted 
to a list. The following examples demonstrate.

```py title="list_examples.py"
empty = list()                 # (1)! 
message = 'Hello'              
letters = list(message)        # (2)!

print(empty)
print(letters)
```

1. Calling `list()` with no arguments creates an empty list `[]`. 
2. Calling `list()` on a `str` type will create a list where each item is a single 
   character from the source string.

Running `list_examples.py` produces the following output in the console.

```pycon
[]
['H', 'e', 'l', 'l', 'o']
```

#### Inspecting Length
The **length** of a sequence is equivalent to the number of items stored in the 
sequence.  Pass a list (or any other sequence) to the `len()` function to see how many 
items are currently stored in the list. 

#### Accessing List Items
There are multiple ways to access list items.  The two most ways to access list items 
are by index and with list iteration in a `for` loop. 

#### List Items by Index
The items in a sequence are stored in the order in which they were defined. An index 
value can be used to access each of the stored items.  In Python, index values start 
from `0`.  For the `nums` variable defined above, the indices are `0, 1, 2`.  Note 
that `nums` stores 3 items.  Since the index starts at `0`, the max index is actually 
`len(nums) - 1` or 2. 

| `nums`       |     |     |     |
|--------------|-----|-----|-----|
| item value  | 1 | 2 | 3 |
| index       | 0 | 1 | 2 |

When you access an item by index, the value is returned.  This value can be used like 
any other value in Python. The following example demonstrates basic index access. 


```py title="list_examples.py"
city_state = ['Memphis', 'TN']
city = city_state[0]
state = city_state[1]
city_state_string = city + ',' + state
print(city_state_string)
```

When we run `list_examples.py` now, the following is output to the shell:

```pycon
Memphis, TN
```

#### Lists in a for Loop
Lists are commonly used to store similar items.  Similar items are often processed 
similarly in a program.  Python `for` loops provide an efficient way to access and 
process every item in a list. 

```py linenums="1"
nums = [1, 2, 3]

for num in nums:        # (1)!
    squared = num ** 2  
    print(squared)   
```

1. The membership expression `num in nums` will extract one element from `nums` and 
   assign it to `num` on each loop run.

The first line in the `for` loop (line 3) instructs the loop to:

1. extract one item at a time from `nums`
2. assign it to `num` 
3. run the loop body (lines 4-5).

This process is referred to as **iteration**.  Here, we are iterating over the items 
in `nums`. Python types that support iteration in this way are called **iterables**. 
Lists are iterables. 

#### List Item Assignment
Python `list` types *support item assignment*. This means that we modify the items in a 
list. For example, if we want to shift all of the values in `nums` by a constant, we 
can do the following in a loop.  Note that we make use of the `range()` function to 
get a sequence of index values.

```py title="list_examples.py"
nums = [1, 2, 3]
offset_value = 10

for k in range(len(nums)):            # (1)!
    nums[k] = nums[k] + offset_value  # (2)!
print(nums)
```

1. `range(len(nums))` is the same as `range(3)`.  This will provide the sequence 0, 1, 
   2 which is used in the loop to access the items by index.
2. Here, one item is accessed by index per loop run. The `offset_value` is added to 
   each and then assigned back to the list item.  This is *item assignment*.

### Tuple Types
The section on lists demonstrated a number of features of sequence types in Python.  
Sequence types support use of the `len()` function for determining length, *indexing* 
for accessing items.  Sequence types also support iteration. Tuples are another 
sequence type that has these same features. Tuples are quite similar to lists. There 
are two differences:

- use `( )` instead of square brackets to define a `tuple`
- `tuple` type variables *do not support* item assignment. 

The following table provides a comparison of tuples and lists:

| feature |  `list`   | `tuple`|
|---|---|---|
| index access | :material-checkbox-marked: | :material-checkbox-marked:|
| len()| :material-checkbox-marked:| :material-checkbox-marked:|
| iteration| :material-checkbox-marked:|:material-checkbox-marked:|
| item assignment | :material-checkbox-marked: |:octicons-x-24:|

Tuples *do not support item assignment.*  Attempting to change an item stored in a 
tuple will lead to an error. Try the following in the Python shell:

```pycon title="Tuples do not support item assignment"
>>> nums = (1, 2, 3)   # (1)!
>>> nums[0] = 11       # (2)!
TypeError                                 Traceback (most recent call last)
Input In [122], in <cell line: 1>()
----> 1 nums[0] = 11

TypeError: 'tuple' object does not support item assignment
```

1. Create a `tuple` containing 1, 2, and 3.
2. Attempt to assign `11` to the item at index `0`.  

Whenever you see a `does not support item assignment` error, it means that the data 
type you are using does not support item assignment: `str` and `tuple` are two such 
types.

### Tuples are Immutable
Tuples do not support item assignment.  This means that once a tuple is defined, it 
can not be modified.  This is an essential feature of tuples called immutability. That 
is to say: tuples are immutable. This is very useful in programs where you need to 
pass data to functions with the assurance that the data will not be modified during 
the program run. 

### Tuples are Lightweight
Tuples require less program memory than lists making tuples a great data type to 
consider when optimizing a program for performance.  

### The `tuple()` Function
This function is used to:

- create an empty `tuple`. Note: this is not very useful accept for comparisons.
- convert a compatible type to `tuple`. Example: `tuple('abc')` yields `('a', 'b' 'c')`


## Range Types
Python's `range()` type is a type that has a very specific purpose--producing a 
uniform sequence of integers. Like `tuples` the `range` sequences are immutable.  
A range type object is created differently compared to other types in Python but they 
are indeed a sequence type. 

### Literals and Variables
Range types are created by calling the `range()` function with a list of arguments 
that specify the desired sequence range and step. The call signature for the range 
function is:

```{: .optional-language-as-class .no-copy}
range(stop)  # or ...
range(start, stop, [step])
```

There are a few different variations on calling range that we need to be aware of to 
use it with master:

- If called with `stop` only, `range()` will return a sequence `0, 1, 2, ..., 
stop-1`.  Note that `stop` is not included in the sequence.
- If called with `start` and `stop` (`step` is optional), then the sequence `1, 2, ...,
  stop-1` is returned.
- When called with all 3 parameters, the `step` argument is the interval between 
  successive elements in the sequence. 

The following examples show a few example ranges:

```py
range(5)           # (1)!
# 0, 1, 2, 3, 4

range(1, 5)        # (2)!
# 1, 2, 3, 4

range(1, 5, 2)     # (3)!
# 1, 3

range(0, -5, -1)   # (4)!
# 0, -1, -2, -3, -4

range(-1, -5, -2)  # (5)!
# 0, -2, -4
```

1. Calling `range()` with `stop` only results in a sequence that starts at 0.
2. Specify `start` to start at a value other than 0.
3. Specify the optional `step` argument to specify the interval between successive 
   sequence elements.
4. `step` can be negative. The results in descending order sequence.
5. The `stop` argument is still not included in descending sequences.

If you try to inspect a `range` type in the Python shell, you will see the function 
call needed to recreate the `range` object you are inspecting.  In other words, the 
*literal* representation of a `range` type is the function call that creates it.  Try 
running the following line in the Python shell:

```py
range(1, 11)
```

You should see the output `range(1, 11)`. 

Range objects can be assigned a names like any other type.  Therefore the following 
works.  We can even check the type like any other type. Try running the following 
lines one at a time in a shell to avoid the need to add `print()` calls.

```py 
my_sequence = range(10, 101, 10)
type(my_sequence)
isinstance(my_sequence, range)
```
The output *when run from the shell* is:

```pycon
>>> my_sequence = range(10, 101, 10)
>>> type(my_sequence)
range
>>> isinstance(my_sequence, range)
True
```

### Range Objects are Lazy
Range objects do not immediately evaluate and return a sequence. This is why we see 
`range(10, 101, 10)` when we inspect the variable `my_sequence` above.  Why is this so?
Well, imagine you defined this range:

```py title="range_examples.py"
big_range = range(10_000_000_000)  # 10 billion integers
print(big_range)
```
Your computer would need to come up with enough free memory to store 10 billion 
integers--an estimated 40 GB.  This is an unreasonable amount of space for a sequence 
that may only be used in a `for` loop. Range objects evaluate the next item in the 
sequence when it is needed (lazy iteration/evaluation). This way, you can loop through 
the range 0 to 10 billion without the memory overhead.

We can coerce a `range` object into another sequence (eager evaluation) by using `list
()` or `tuple()`.  The following example demonstrates:

```py
my_sequence = list(range(10, 101, 10))
print(my_sequence)
```

Which outputs:

```py
[10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
```

## Dictionary Types
Mapping types are referred to as Dictionaries in the Python vernacular.  In Python 
mappings are implemented by the `dict` type. Mappings map lookup *keys* to *values* in a 
one-to-one, directional relationship. This is similar to dictionaries used for 
language.  When we look up a word in glossary or dictionary, we locate the definition. 
In this analogy, the words are keys and the definitions are values. 

We can create our own language dictionary using a `dict` in Python. Here, the 
definitions are shortened from the [Oxford English Dictionary](https://www.oed.com). 

```py title="dict_examples.py"
definitions = {
    'tree': 'a woody perennial plant.',
    'shrub': 'a woody plant which is smaller than a tree',
    'bush': 'a shrub or clump of shrubs',
    'hedge': 'a fence or boundary formed by closely growing bushes or shrubs'
}

# Get the definition of tree
tree_definition  = definitions['tree']
print(f'tree: {tree_definition}')
```

This program outputs:

```pycon
>>>
tree: a woody perennial plant.
```

### Literals and Values
Define a dictionary in Python by enclosing a comma-separated list of `key: value` 
pairs with curly-braces `{}`. The following example maps country codes (keys) to 
country names (values).

```py title="dictionary_examples.py"
codes_countries = {'US': 'United States', 'IN': 'India'}
country = codes_countries['IN']
print(f'Code IN is for {country}')
```

Output:

```pycon
Code IN is for India
```

### The `dict()` Function
This function is used to:

- create an empty dictionary. Example `dict()` yields `{}`.
- create a new dictionary from keyword arguments. See example below.

This example uses the `dict()` function to define the `codes_countries` dictionary 
above. Try running this in a Python shell to see that it is equivalent to the previous 
example.

```py title="dictionary_examples.py"
codes_countries = dict(US='United States', IN='India')  # (1)! 
country = codes_countries['IN']
print(f'Code IN is for {country}')
```

1. Note that string keys to not need quotes when using the `dict()` function to define 
   a dictionary.

Dictionaries have a full chapter devoted to them where they are covered in more detail.
We know turn our attention to Sets.

## Set Types
Python sets are *unordered* collections of unique Python objects.  Python sets are 
implemented by the `set` type. Set types can only store certain types. This type 
requires a good bit of additional discussion that is covered in a later chapter.  For 
this gentle introduction to `set` types covers only built-in Python types that can be 
stored in a set. 

Sets are used to:

- remove duplicates from other types like lists and tuples.
- perform mathematical set operations like intersection and union.

### Literals and Values
Define a `set` variable using a `set` literal which is a comma-separated sequence of 
objects enclosed in curly braces `{ }`. The following example defines a set of words. 
Note that even though the word "shrub" is included twice, there is only one such value 
stored in the resulting set.

```py
woody_plants = {'tree', 'shrub', 'bush', 'hedge', 'shrub'}
print(woody_plants)
```

Running this example results in the following output. Note that the order is not 
preserved. Sets are *unordered* collections. 

```pycon
{'shrub', 'tree', 'hedge', 'bush'}
```

!!! caution
    Sets and dictionaries both use curly braces `{ }` as delimiters. The two can be 
    easily distinguished from each other because `set` types do not contain any `:`. 
    Note also that an empty `dict` literal is `{}` whereas an empty `set` literal is 
    `set()`. 

### The `set()` Function
This function is used to:

- create an empty `set` type. Example: `set()` yields `set()`.
- create a set from another compatible type. Example `set('abc')` yields `{'a', 'b','c'}`.


## Style Notes
PEP8 guidelines make several recommendations that apply to many of the types covered 
here.  The following examples demonstrate how to follow these widely accepted guidelines. 

### String Delimiters
In Python, single and double quotes are equivalent. PEP8 makes no recommendation as to 
which one to use for string delimiters.  Decide which one you prefer and use it 
consistently throughout a single codebase.[^1]

[^1]: See [PEP8 String Delimiters](https://peps.python.org/pep-0008/#string-quotes)

```py
# WRONG:
first_name = "Jack"
last_name = 'Handy'    # mixed quote types for strings
```

```py
# CORRECT:
first_name = 'Jack'
last_name = 'Handy'    # pick one type and use it consistently
```

### Sequences
Sequences of values or variables are used when defining lists, tuples, dictionaries, and 
sets. PEP8 makes a general recommendation that a space be included after *any* comma 
that is not at the end of a line. When defining these types, include these spaces.[^2]

The following examples demonstrate:

```py
# WRONG:
nums = [1,2,3]
```

```py
# CORRECT:
nums = [1, 2, 3]
```

```py
# WRONG:
codes_countries = {'US': 'United States','IN': 'India'}
```

```py
# CORRECT:
codes_countries = {'US': 'United States', 'IN': 'India'}
```

```py
# WRONG:
woody_plants = {'tree','shrub','bush','hedge'}
```

```py
# CORRECT:
woody_plants = {'tree', 'shrub', 'bush', 'hedge'}
```

### Spaces After `:`
When defining dictionaries, include a single space after every semicolon `:`.



```py
# WRONG:
codes_countries = {'US':'United States', 'IN':'India'}
```

```py
# CORRECT:
codes_countries = {'US': 'United States', 'IN': 'India'}
```

## Summary
This concludes a rather broad survey of basic Python types. Each of these types 
receives detailed coverage in later chapters.

## Related Links
- [Official Documentation - Built-in Types](https://docs.python.org/3/library/stdtypes.html)
