## Errors are Inevitable
The previous section demonstrated some very simple Python code statements. Hopefully, 
you successfully replicated the examples.  Once you get beyond simple statements 
you'll inevitably encounter errors. Be patient as this is common even for 
professionals with years of experience with the language. 

!!! quote
    A different error message! Finally some progress![^1]

[^1]: The most upvoted post on devRant. Via [bakablah](https://devrant.com/rants/17426/a-different-error-message-finally-some-progress)

## Errors: Two-types
The two types of error messages that you'll encounter are *syntax errors* and *runtime 
errors*. Syntax errors result from the violations of the basic rules of Python 
structure whereas runtime errors are usually the result of mistakes in the program 
logic. Naturally, we want to correct errors. Of the two, syntax errors 
are the simplest to address.

### Syntax Errors
Syntax errors are mistakes in the structure of the text of the Python source code. 
The `print()` function, for example is a Python function.  When we use the print 
function, we type the *name* of the function, followed by `(` followed by the 
expression to print, followed by `)`. 

```python
>>> print("Look ma! No errors!")
Look ma! No errors!
```

If we enter this code into the editor and leave out the last `)`, we introduce a 
syntax violation. Different editors handles this in different ways.  IDLE will not 
warn you about this until you attempt to run the code.  Let us attempt this example in 
IDLE.

- enter the following code into an editor window in IDLE
- save the file to a suitable file name (example: `errors.py`)
- run the module with "Run -> Module" (or ++F5++)

```python
print(5 + 2
```

When we enter this code in IDLE, we receive no indication of an error.  When we run 
the module, however, IDLE displays an error dialog.

<figure markdown>
![Syntax Error](img/01-errors-syntax-basic.png#light-only){width="500"}
<figcaption>IDLE presents an error dialog for syntax errors.</figcaption>
</figure>

When we dismiss the dialog, the location of the error is highlighted in the editor 
window.Note that the location of the highlight is not *exact*, but it does provide 
enough context to make the correction. 

<figure markdown>
![Syntax Error](img/01-errors-syntax-basic-highlighted.png#light-only){width="500"}
<figcaption>IDLE highlights the location of syntax errors.</figcaption>
</figure>

!!! note
    Sometimes, a syntax error is highlighted on a different line from the actual 
    location of the actual error.  This can be misleading. A simple method in this 
    case is to inspect both the highlighted line *and* the preceding line. 

Various editors handle syntax errors in different ways. For example, PyCharm will 
automatically add the closing `)` when you enter `(`, which is helpful in avoiding 
such errors.  If we delete the closing paren while editing further, PyCharm will 
annotate the error with a red squiggle line along with a hover tooltip. 

<figure markdown>
![PyCharm annotates](img/01-errors-syntax-basic-pycharm.png){width="500"}
<figcaption>PyCharm annotates syntax errors as we edit.</figcaption>
</figure>


### Runtime Errors