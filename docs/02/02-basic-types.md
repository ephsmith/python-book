## Introduction
In software programming data types are an important concept. Python programs can 
operate on a variety of types of data.  Different types are handled differently in a 
Python program so it is important to understand the basic types that Python provides.

Python data types fall into two categories: 
- simple or atomic data types: can not be decomposed into a collection of another type
- non-atomic data types: are composed of other types

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
non-atomic compositions of an atomic character type. This is not the case in Python.  
The only text type in Python is the `str` type. 

### `str` Literals
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

### `str` Variables
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















