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

## Text Type: `str`
Many other languages have multiple text types. In C++, for example, strings are 
non-atomic compositions of an atomic character type. This is not the case in Python.  
The only text type in Python is the `str` type. 

### `str` literals
A **literal** is an actual value of a certain type that is included in our code. 
String literals are entered as characters, surrounded by (delimited with) single or 
double quotes.

The following simple program includes some string literal examples.

```python title="string_examples.py"
country_code = 'CA'
product_code = "EZ123"
print(country_code, product_code)
```

When we run this program, the following is printed to the screen.

```python
>>>
CA EZ123
```

### Long String Literals
The PEP8 style guide requires that lines are no longer that 79 characters in width.  
This poses a challenge when we need to include long lines of text in our program. 
This section covers multiple approaches to dealing with long lines. 

#### Breaking Long Lines with Parentheses
Python ignores any whitespace between parentheses. We can use this to our advantage 
when breaking long lines.  Note in the following example that Python concatenates 
(puts together) the two string literals contained between the parens.

```python
>>> message = ("Hello "  "there!")
>>> print(message)
Hello there!
```

We now see that Python concatenates multiple strings when they are contained within 
parentheses.  Let's use this feature to break up a long line. Copy and paste this into 
an editor window and run it to see this in action.

```python title="string_examples.py"
very_long_line_of_text = (
    "Do all the good you can, by all the means you can, in all the ways you can,"
    "in all the places you can, at all the times you can, to all the people you can," 
    "as long as ever you can."
)

print(very_long_line_of_text)
```

And when we run `string_examples.py`, we see:

```
>>>
Do all the good you can, by all the means you can, in all the ways you can,in all the places you can, at all the times you can, to all the people you can,as long as ever you can.
>>>
```

Breaking long lines with parens is the cleanest approach to solving this problem in my 
opinion. There is another commonly used approach.

#### Escaping Newlines with `\`
The line continuation character `\` (backslash) instructs Python to ignore the newline 
character that follows.  This can be used to break up long strings or other long lines.
The modifications to `string_examples.py` below demonstrate this. Run the code 
yourself to see it in action and experiment with changes. The code does indeed print 
the same result as the last version. 

```python title="string_examples.py"
very_long_line_of_text = "Do all the good you can, by all the means you can,"\
    " in all the ways you can, in all the places you can, at all the times you"\
    " can, to all the people you can, as long as ever you can."

print(very_long_line_of_text)

```

### String Literals within Triple Quotes
In the previous section, we saw how to ignore newlines in string literals. 
What if we want to *preserve* newlines and other spacing in our string 
literals? Enclosing a string literal in triple single or triple double quotes 
accomplishes this.  Consider the text of a poem for example.  Poems tend to have very 
specific formatting needs.  The following classic poem by Langston Hughes is an 
example as Mr. Hughes used indentation and spacing in his style.

``` title="Harlem, By Langston Hughes"
What happens to a dream deferred?

      Does it dry up
      like a raisin in the sun?
      Or fester like a sore—
      And then run?
      Does it stink like rotten meat?
      Or crust and sugar over—
      like a syrupy sweet?

      Maybe it just sags
      like a heavy load.

      Or does it explode?
```

Surrounding such a block of text with triple double or triple single quotes will 
preserve all whitespace (tabs, spaces, newlines). Try adding the following code block 
to `string_examples.py` and running it to see this technique in action. 

```python title="string_examples.py"
harlem = \
"""What happens to a dream deferred?

      Does it dry up
      like a raisin in the sun?
      Or fester like a sore—
      And then run?
      Does it stink like rotten meat?
      Or crust and sugar over—
      like a syrupy sweet?

      Maybe it just sags
      like a heavy load.

      Or does it explode?
"""

print(harlem)
```

#### Triple-quoted Strings: Potential issues
The whitespace preservation of triple-quoted strings is both a benefit and a 
problem--depending on the situation.  Consider the situation illustrated below.  The 
`harlem` variable from the previous section is now included in a function--note the 
additional indentation.  The triple-quote's whitespace preservation keeps the 
additional indentation spaces in addition to the space in the original text. Note the 
result when you run this code.

```python title="string_examples.py"
def print_poem():
    harlem = \
    """What happens to a dream deferred?

          Does it dry up
          like a raisin in the sun?
          Or fester like a sore—
          And then run?
          Does it stink like rotten meat?
          Or crust and sugar over—
          like a syrupy sweet?

          Maybe it just sags
          like a heavy load.

          Or does it explode?
    """
    print(harlem)

if __name__ == '__main__':
    print_poem()
```

Here's the output.  Do you notice the additional spaces?  Keep this in mind as a 
potential hazard to look out for. 

```
What happens to a dream deferred?

          Does it dry up
          like a raisin in the sun?
          Or fester like a sore—
          And then run?
          Does it stink like rotten meat?
          Or crust and sugar over—
          like a syrupy sweet?

          Maybe it just sags
          like a heavy load.

          Or does it explode?
```
















