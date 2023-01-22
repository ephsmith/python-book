## Strings Review
The `str` type was first introduced in [Text Type](../02/02-basic-types.md#text-type-str).
Here are some high-level `str` facts that were covered in that section:

- Use double (`"`) or single (`'`) quotes to *delimit* string literals.
- Calling `type()` on a `str` type will return the string `'str'`.  
- You can verify if a variable is a `str` type with `isinstance()`.
- Strings can be concatenated using the `+` operator. 

## String Indexing
Python `str` types are sequence types composed of 1 or more `str` types.  This is a 
strange way to describe them, but it is true.  We can the items in a string using 
square bracket indexing where the index values start at `0` and end at `length - 1` 
where `length` is the length of the string. 

```py
letters = 'ABCD'  # (1)!
A = letters[0]    # (2)!
B = letters[1]
C = letters[2]
D = letters[3]    # (3)!
```

1. `letters` is a `str` of length 3.  
2. The first index is `0`
3. The final index (the index of the last text character) is length - 1 or 3 in this case.

## Slicing
Slicing is an operation that all sequence types have in common. Slices provide a way to 
index multiple parts of a sequence. For strings, slices are sub strings of the parent 
string.  To slice a string, index with the pattern `[start:stop:step]` (similar to 
`range()` arguments).  Note that `stop` is not included in the output.  Indices from 
`start` to `stop - 1` are returned.  The `step` controls the numerical distance 
between each of the indices in the slice.  The following examples demonstrate.

```py title="slice_example_1.py"
full_name = 'Albert Einstein'
first_name = full_name[:6]    # start defaults to 0   
last_name = full_name[7:]     # end defaults to the last index + 1
print(f'first_name = {first_name}')
print(f'last_name = {last_name}')
```

```py title="slice_example_2.py"
numbers = '0123456789'
multiples_of_two = numbers[::2]    # step is two
multiples_of_three = numbers[::3]  # step is three
print(f'multiples_of_two = {multiples_of_two}')
print(f'multiples_of_three = {multiples_of_three}')
```

### Named Slices
Named slices are useful when a slice needs to be reused. The `slice()` function can be 
used to assign a slice object to a name which can then be used to slice other 
sequences. Pass at least one of `start`, `stop`, `step` to `slice()` and fill any 
missing arguments with `None`.  We can re-code `slice_example_2.py` with named slices:

```py
numbers = '0123456789'
twos_slice = slice(0, None, 2)
threes_slice = slice(0, None, 3)
multiples_of_two = numbers[twos_slice]    # step is two
multiples_of_three = numbers[threes_slice]  # step is three
print(f'multiples_of_two = {multiples_of_two}')
print(f'multiples_of_three = {multiples_of_three}')
```

Parsing fixed-width field (FWF) files is a common use case for named slices. FWF files 
store data in columns of a fixed length of characters and are a common format for 
importing to and from databases.  The following is an example of a FWF data file:

```text title="countries.txt"
IN India                New Delhi
NL Netherlands          Amsterdam
US United States        Washington D.C.    
```

In `countries.txt`, the columns occupy the following ranges of characters:

```text title="column ranges"
COUNTRY_CODE: [0, 1,]
COUNTRY_NAME: [3, 4, ..., 22]
COUNTRY_CAPITAL: [24, 25, ..., 43]
```

We can name slices for the fields for reuse and increased readability:

```py title="slice_countries.py"
CODE = slice(0, 2)
NAME = slice(3, 23)
CAPITAL = slice(24, 44)
# (1)!
countries_fwf = """IN India                New Delhi
NL Netherlands          Amsterdam
US United States        Washington D.C.    
"""

# Consume each field and print only the capital
for line in countries_fwf.splitlines():    # (2)!
    code, name, capital = line[CODE], line[NAME], line[CAPITAL] 
    print(capital.strip())    # (3)!
```

1. `countries_fwf` is a triple-quoted string which preserves formatting.  This is a 
   fixed-width field formatted string using the field widths defined above.
2. The `splitlines()` method is a string method that splits a string object on line 
   breaks and returns a list where each item is a line. 
3. The `strip()` method is a string method that removes any spaces, newlines, tabs 
   (whitespace) from the *beginning* or the *end* of a string. 

Without the use of the `strip()` method, the additional spaces in the name and capital 
fields would still be present. Many other useful string methods are covered later on 
this page.

## Converting Numbers to Strings

## f-Strings
- f-strings, added in Python 3.6, simplified string formatting
- strings preceded by `f` are considered f-strings
- Any Python expression enclosed in `{}` is replaced with its value in the returned 
  string.


```py
lang = "Python"
ver = 2.4

formatted = f"My first {lang} version was ver {version}"

print(formatted)
```

### f-strings (new in 3.8)
- Python 3.8 introduced the debugging specifier `=`
    - prints the expression, followed by `=`, followed by the value of the expression
- useful for debugging and logging.

```py
print(f"{lang=}\n{ver=}")

a, b = 2000, 22

print(f"\n{a + b = }")
```

## Format Specificiers
- control how numbers (and other types) are printed
- included at the end of the `{}` placeholder

This example demonstrates a basic use case. Note that USD currency rarely includes fractional cents.

```py
subtotal = 1.49
tax = 0.33
total = subtotal * (1 + tax)

msg = f"The total is $ {total}"

print(msg)
```

### Specify Precision
- Use `{:.[precision]f}` with floating point types to limit the number of decimal places to `precision` places.

```py
msg = f"The total is $ {total:0.2f}"

print(msg)
```

### Other Format Control Options
The full format control string allows for the following fields:

#### Type
The type specifier `type` provides representation conversion for numbers. 

``` text
[fill][align][sign][width].[precision][type]
```

```py title="type_specifiers.py" linenums="1"
num = 224
print(f'with d: {num:d}')  # this is the default for integers
print(f'with f: {num:f}')  # floating point display
print(f'with x: {num:x}')  # lowcase hexadecimal representation
print(f'with X: {num:X}')  # UPCASE hexadecimal representation
print(f'with b: {num:b}')  # binary representation
print(f'with o: {num:o}')  # octal representation

print(f'with f: {num:f}')  # default for floating point types
print(f'with e: {num:e}')  # lowcase exponential (scientific) notation
print(f'with E: {num:E}')  # UPCASE exponential notation
print(f'with %: {num:%}')  # With %, the value is first multiplied by 100
```

```text title="Output for type_specifiers.py (Line numbers match the associated source line)" linenums="2"
with d: 224
with f: 224.000000
with x: e0
with X: E0
with b: 11100000
with o: 340
with f: 224.000000
with e: 2.240000e+02
with E: 2.240000E+02
with %: 22400.000000%
```

#### Field Width

Control the width of the field (as in FWF formatting) with the width field in the 
format string.

```
[fill][align][sign][width].[precision][type]
```

```py title="field_width.py" linenums="1"
subtotal = 1.49
tax = 0.33
total = subtotal * (1 + tax)

print(f"total: {total:0.2f}")
print(f"total: {total:10.2f}")
print(f"total: {total:20.2f}")
```

```text title="Output of field_width.py (Line numbers match the associated source line)." linenums="5"
total: 1.98
total:       1.98
total:                 1.98
```

#### Sign
- **sign**: the sign option is only valid for number types. 
  - `+`: indicates that a sign should be used for both positive as well as negative numbers.
  - `-`: indicates that a sign should be used only for negative numbers (this is the default behavior).
  - ` `: (space) indicates that a leading space should be used on positive numbers, and a minus sign on negative

```
[fill][align][sign][width].[precision][type]
```

```py title="sign.py" linenums="1"
subtotal = 1.49
tax = 0.33
total = subtotal * (1 + tax)

print(f"total: {total:+.2f}")
print(f"total: {-total:-.2f}")
print(f"total: {total: .2f}")
print(f"total: {-total: .2f}")
```

``` text title="Output of sign.py (Line numbers match the associated source line)." 
linenums="5"
total: +1.98
total: -1.98
total:  1.98
total: -1.98
```

## String Methods
- Methods are functions (like `print()`) that are "*attached*" to objects.
- String methods are functions attached to `str` objects.  
- Use the `.method()` pattern for calling
- Some useful methods:
    - `.upper()`, `.lower()`, `.title()`
    - `.strip()`, `.rstrip()`, and `.lstrip()`
    - `.startswith()`, `.endswith()`
- `.split()` and `.splitlines()` are string methods that return `list` types. 

### String Methods (new since 3.9)
- `.removeprefix(prefix)`: removes the prefix substring `prefix` if present.
- `.removesuffix(suffix)`: removes a suffix if present. 

