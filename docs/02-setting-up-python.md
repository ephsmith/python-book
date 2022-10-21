## Downloading Python
The Python version supported by this text is version **3.10.x** (note
that the `x` can be any number). When downloading Python, please be
sure to select this version.

Official Python releases are available from the official [Python
Page](https://www.python.org). The site auto detects your operating
system and provides a link to the most current version. If the target
version is not listed, you can visit the [All
Releases](https://www.python.org/downloads/) page to locate it.


## Installing Python
For installation instructions, I will lean on the expertise of the
RealPython team. This platform maintains up-to-date, community
reviewed instuctions and articles on many Python related topics.

Visit the RealPython [installation
instructions](https://realpython.com/installing-python/) for an
up-to-date guide on installing for your operating system and platform.

!!! danger "For Windows Users..."


    Do not install the Microsoft Store version of Python. Be sure to
    install the package available from the official Python page.


## Using the IDLE IDE
An IDE (intgrated development environment) typically includes:

- an editor for editing code
- a method for building / running code
- a debugger for tracing program execution and troubleshooting errors

Python programs are simply text files, so you can technically use your preferred
*plain text editor* to edit Python code. However, you will need to
rely on the operating system shell / terminal to run your code using
the Python interpreter.

An IDE simplifies your workflow when editing and running programs. For
first time Python users, IDLE is a great choice for many reasons:

- IDLE is installed when you install Python using the official
  installer.
- IDLE is preconfigured and ready to use for Python development.
- IDLE is simpler than most IDEs.

This text will refer only to IDLE when showing examples that involve
an IDE.

### Launching IDLE
Launch IDLE using your favorite launch method. On most operating
systems, the search feature is typically the fastest.

- On Windows, press the Windows key and start typing IDLE
- On macOS, type Command + SPACE and start typing IDLE

When IDLE launches, you will be greeted by a window containing the
Python shell. We'll refer to this as the "shell window" or
"interactive window".  The interactive window lets you interact with
the Python interpreter directly by entering code statements and
viewing the result.


<figure markdown>
  ![Python Shell](img/02-python-shell.gif){ width="500" }
  <figcaption>Python Shell / IDLE Interactive Window</figcaption>
</figure>


### Introducing the Python Shell
The default Python shell provides a simple Read-Evaluate-Print-Loop
(REPL) interface to the Python interpreter. You are greeted with the
Python shell when you start IDLE or launch the shell directly from an
OS shell.

Take a moment to explore the basic parts of the Python shell using the
annotations below.

```py
Python 3.10.0 (v3.10.0:b494f5935c, Oct  4 2021, 14:59:19) [Clang
12.0.5 (clang-1205.0.22.11)] on darwin # (1)!
Type "help", "copyright", "credits" or "license()" for more
information. # (2)!

>>> # (3)!
>>> print('Hello World!') # (4)!
Hello World # (5)!
>>>
```

1. The Python version (here, 3.10.0) is shown at the beginning of a
   Python shell session.

2. Don't overlook `help` here. Python's help feature is, well,
   helpful.

3. The `>>>` shown here is the Python shell prompt. Never enter these
   characters explicitly when pasting example code.

4. Enter a single line of Python code like this one. When you press
   +Enter+, the Python interpreter *reads* and *evaluates* the
   code. It then *prints* the result.

5. The Python interpreter *prints* the result. Note the absences of
   the `>>>` prompt on the result line.



!!! note

	The term "shell" is more commonly used to refer to an operating
	system command line interface such as CMD.exe on Windows or
	Terminal.app on macOS. "Python shell" will be used whenever
	referring to Python.

### Use Python as a Calculator
You can use the Python shell as a simple calculator. Python arithmetic
expressions use the following operators.

|example operation|result|mathematical operation|
|-----------------|------|----------------------|
|`2 + 5`          | `7`  | addition             |
|`2 - 5`          | `-3` | subtraction          |
|`5 / 2`          |`2.5` | float division       |
|`5 * 2`          |`10`  | multiplication       |
|`2 ** 5`         |`32`  | exponentiation       |
|`5 // 2`         |`2`   |integer division      |
|`5 % 2`          |`1`   |modulus operator      |

When you enter one of these expression at the Python shell prompt the
result will be printed below the prompt.

![Python as a calculator](img/02-shell-calculator.png)

### Add Some Variables
Variables are names (symbols) that refer to a value. In order to use a
variable, a value must be assigned to it using the *assignment
operator* `=`. Experimemnt with this a bit using single character
variable names.

```py
x = 5  # (1)!
y = 2  # (2)!
x + y  # (3)!
```

1. The symbol (name) `x` now refers to the value `5`.

2. The symbol `y` now refers to the value `2.

3. In evaluating this expression, the Python interpreter retrieves the
   values referred to by the names (`x` and `y`) before evaluating the
   arithmetic expression.

#### Rules for Names in Python
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

### Keyboard Shortcuts in the Shell

|shortcut|operation|
|--------|---------|
|++ctrl+p++|previous history|
|++ctrl+n++|next history|
|++ctrl+a++|beginning of line|
|++ctrl+e++|end of line|

It is also worth noting that the previous result is always stored in
the varaible `_`.  You can access this instead of copying and pasting
a result. Example shell session:

```py
>>> x = 5
>>> y = 2
>>> x + y
7
>>> _ + 10 # (1)!
17
```

1. `_` is a special Python shell variable that stores the result of
   the last expression evaluated by the interpreter. Use this instead
   of copying and pasting.

### The Editor Window
The Python shell is an essential development tool for quickly
prototyping ideas. In a typical software development workflow, use of
the Python shell is typically short-lived because we need our code to
reside in a place where it can be re-used--in a file. We use the IDLE
editor window for this.

Files that contain Python code are referred to as Python *scripts*,
*modules*, or simply Python files.

- **script**: a file containing Python code that is meant to be run
  directly--like a standalone program/application.
- **module**: A module is a file containing Python code that can be
  imported by other Python scripts or modules. (*Note that Python
  modules can also be run directly.*)

#### Edit and Run a Python Module
When IDLE launches, only the Python shell window is displayed for
use. You can open an editor window by selecting `File -> New
File`. *Try this now* and enter the following calculator code into the
resulting window.

```py
x = 5
y = 2
x + y
```

You'll need to save this file with a Python extension `.py` before you
can run it.

1. Choose `File -> Save` (or ++ctrl+s++ on
   :fontawesome-brands-windows:, ++command+s++ on
   :fontawesome-brands-apple:)
2. Choose a file location and save the file as `calculate.py`.

Now that you have saved the file, you can run the file using `Run ->
Run Module`. *Note that there is a keyboard shortcut for this as
well*--(++f5++)

If you entered the exact code above in the file, you'll notice that
there is no output when you run the module. This is one key difference
between the editor and the Python shell. *The Python shell always
displays the result of an expression*.  When we run a module, the
result of every expression is *not* printed to the screen. In order to
view the results of expressions, we must use the `print()` function.

Modify your code to include the modifications shown below:

```py
x = 5
y = 2
print(x + y) # (1)!
```

1. Use `print` to display the result of (or value of) an expression.

### Learn Python with IDLE
As you progress through the course, you will encounter many new
language features. You can *accelerate* your learning by interacting
with these features as soon as you encounter them. Use the Python
shell to quickly try out Python code snippets found in this text. When
code snippets begin to evolve into something you want to experiment
with a bit more, use the editor to maintain the code in an editable
file which you can run again and again.

Here are some tips for learning with IDLE:

- Keep IDLE open while working through this text.
- Click the *copy to clipboard* icon next to any code in this text to
  copy the code.
- Paste the code into the Python shell to quickly view a result.
- Re-paste the code and make some modifications.
- Collect code snippets in a Python module for further modifications
  * recall that you need to add `print()` to print any results that
    are not already printed.

## Other IDEs
It is highly recommended that you use IDLE initially if you are a
just getting started with the Python language. IDLE is installed when
you install Python from [the offical Python
site](https://www.python.org). Moreover, IDLE requires no additional
configuration and its minimal interface keeps the focus on the
language.

As you become more comfortable with the language, you'll inevitably
long for a more feature rich environment for developing Python code.

### Microsoft Visual Studio Code
[Visual Studio Code](https://code.visualstudio.com/download) is a widely used IDE. VS Code is has strong support
for Python via extensions.  Visit the [Real Python article](https://realpython.com/python-development-visual-studio-code/) on setting
up VS Code for Python development.

Thoughts on VS Code:

- VS Code requires a bit of configuration before it is in a usable
  state for Python development.
- VS Code is freely available and runs on most platforms.

### Pycharm
[Pycharm](https://www.jetbrains.com/pycharm-edu/) is a JetBrains product.  The
education version is free, but you will need to verify student
status--the process is simple and worth it. Visit the [RealPython
article](https://realpython.com/pycharm-guide/) on using PyCharm for
development.

!!! note
    PyCharm is a highly recommended IDE. Give it a try once you have
    some minimal experience programming Python with IDLE.

    PyCharm educational licenses are quite easy to obtain. Be sure to 
    get the educational version (not the community edition). 
    PyCharm integrates
    well with all Python environments and GitHub.  It also supports
    notebooks.  All of this comes with very minimal configuration compared
    to Jupyter and VS Code. 

Thoughts on PyCharm:

- PyCharm requires much less configuration compared to VS Code
- PyCharm is designed as a Python first IDE, so it is ready for Python
  development.
- PyCharm feels like more of a professional product compared to VS
  Code. This is, of course, subjective.
- PyCharm runs on Windows or macOS.


### Jupyter Notebooks
Jupyter Notebooks are a great way to develop Python. Jupyter Notebooks
provide a browser based editing environment for Python. In a notebook,
code is entered into "cells".  Cells can be evaluated any number of
times and the result is printed below the cell. Notebooks fill
the functional space between the Python shell and an editor. In a
notebook, the results of expressions are printed below once evaluated,
but the code remains in an editable state after execution. Notebooks
also provide the ability to document / annotate your code using
special [Markdown](https://www.markdownguide.org) cells. If a graphics
enabled Python library is used in a Jupyter notebook, the graphics are
displayed inline in the Notebook.  All of these features make
notebooks the most visual way to develop Python.

Visit the
[RealPython](https://realpython.com/jupyter-notebook-introduction/)
article on getting started with Jupyter Notebooks.

Thoughts on Notebooks:

- Notebooks are a great way to learn and develop Python
- Notebooks are widely used in the data science and academic domains
- Notebooks are very visual--graphics and results are displayed
  alongside the code that produced them.
- **Caution**: Notebooks can lead to strange issues related to execution
  order. Example: it is possible to run a cell that depends on another
  cell before the prerequisite cell is executed.  This can lead to
  confusing or erroneous results and care must be taken to avoid this
  issue.
- **Side benefit**: The [IPython](https://ipython.readthedocs.io/en/stable/) shell is installed when you install
  Jupyter Lab or classic Jupyter Notebooks. This advanced Python shell
  has many wonderful features.
