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

## Determining the Type of a Variable
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






















