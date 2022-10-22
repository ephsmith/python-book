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

- Sequences: `list`, `tuple`
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
>>>
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

## Sequence Types
Coming soon.

- Lists and Tuples

## Mapping Types
Coming soon.

- Dictionaries

## Other Types

Coming Soon

- Sets: `set`, `frozenset`
- Binary Types: `bytes`, `bytearray`
