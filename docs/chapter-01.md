## Why learn Python?
You may already have an answer to this question. In this session we'll
assume you still have doubts and attempt to answer the question "Why
should I learn Python?".

There are myriad reasons to learn Python that are different depending
on your field of interest. There are various industry domains where
Python shines (links available at the bottom of this page):

- web development
- information technology
- data science

Within these industry sectors there are other options however. In data
science for example [R](https://www.r-project.org) and SQL are both
widely used languages. For web development, there are a host of other
languages that can be used as web-backends: PHP, Node, and Java to
name a few. *Why learn Python?*

Any attempt to answer this absolutely is a foolish endeavour. There
are, however, several strenghts of the Python language that make it a
standout choice.

- Python is freely to download and use.
- Python runs on all major architectures and operating sytems.
- Python is a general purpose programming language.
- Python has a *very* clean and readable syntax.
- Python is popular!

Simply listing these attributes of Python in a list may not be
enough. The next few sections expand upon each.

## Python is freely available
Python is open source and licensed in a manner that makes it agreeable
with many coporate applications based on the language. Python can be
used to create professional products without license fees or license
requirements.

You can read more about Python licenses on the [History and
License](https://docs.python.org/3/license.html) page of the official
Python site.

## Python runs on all major architecutres
[Official Python installation packages](https://www.python.org/downloads/release/python-3108/) are available for X86, ARM, and
Apple M-series architecures for both Windows and macOS. Linux and UNIX packages
are made available by package maintainers via the source releases made
available on the official Python site.

## Python is general-purpose.
If Python is specialized for anything, it is being a useful language
in just about every computing domain. Python finds uses in everything
from simple system adminstration tasks to full-fledged GUI
applications. Given its popularity, there are many official and 3-rd
party Python libraries that extend the language's use cases across a full spectrum of computing / development tasks.

- Create a web-app:
  [Flask](https://flask.palletsprojects.com/en/2.2.x/),
  [FastAPI](https://fastapi.tiangolo.com)
- Download files from the web or query a web API: see
  [Requests](https://requests.readthedocs.io/en/latest/)
- Administer remote machines: [Fabric](https://www.fabfile.org)
- Data Engineering / Data Science: see examples on
  [Kaggle](https://www.kaggle.com/code?language=Python)
- Big-Data: see
  [PySpark](https://spark.apache.org/docs/3.1.3/api/python/index.html)

## Python syntax is minimal and clean
Syntax refers to the rules that define the structure of the
language. Syntax rules specify the meaning of and relationships
between symbols in the language. A clean language syntax makes that
language easier to read.

!!! quote

    Indeed, the ratio of time spent reading versus writing is well
	over 10 to 1. We are constantly reading old code as part of the
	effort to write new code. ...[Therefore,] making it easy to read
	makes it easier to write.

	Robert C. Martin, Clean Code: A Handbook of Agile Software Craftsmanship

To illustrate the simplicity of Python syntax in comparison to other
languages, consider *grouping syntax*. In C++ and Java for example,
code is grouped using `{}` characters. The C++ source below
illustrates this.

```cpp title="bubble_sort.cpp"
void bubbleSort(int array[], int size) { // (1)!

  for (int step = 0; step < size; ++step) { // (2)!

    for (int i = 0; i < size - step; ++i) {

      if (array[i] > array[i + 1]) {

        int temp = array[i]; // (3)!
        array[i] = array[i + 1];
        array[i + 1] = temp;
      }
    }
  }
}
```

1. Curly braces `{}` group lines of code together. Note that
   indentation is also present.
2. Complicated `for` loop step arguments.
3. Semicolons `;` must be present on all code statements.

Compare the C++ code above to the equivalent Python implementation
below. Note the absence of grouping characters. This is because the
grouping syntax of Python relies on the *indentation* of the
lines--not special characters that lead to visual clutter.

```py title="bubble_sort.py"
def bubble_sort(array):

  for j in range(len(array)): # (1)!

    for k in range(len(array) - j - 1): # (2)!

      if array[k] > array[k + 1]:
        array[k], array[k+1] = array[k+1], array[k] # (3)!
```

1. Simplified `for` loop expressions.
2. Indentation is all that is needed to group code together.
3. No semicolons `;` are needed for any Python language statements.

Some of Python's simplicity is owed to the simplicity of its built-in
functions.  Compare the two implementations of "Hello World!" below.

```cpp title="C++ version: hello.cpp"
#include <iostream>

int main() {
    std::cout << "Hello World!";
    return 0;
}
```

```py title="Python version: hello.py"
print("Hello World!")
```

The simplicity of the Python implementation is owed to the simplicity
of the built-in `print()` function.

In summary, Python's clean and readable syntax makes it easier to read
and write the lanugage. It also reduces the number of potential syntax
errors.

## Python is Popular
As of October 2022, Python was *number 1* on the [TIOBE
Index](https://www.tiobe.com/tiobe-index/) of programming
languages. This index can be used to make a strategic decision about
which language to learn. In short, Python is currently the most
popular language in terms of usage according to the index.

Popular languages bring with them many benefits:

- better security and stability (more contributors and financial
  support)
- more third-party libraries (get more done with less)
- supportive learning community (many available learning resources)

## Summary
There is no reason to settle on learning only one programming
language. However, in 2022, Python is an excellent choice. This still
depends largely upon your target field.

If this is your first venture into the world of software programming,
Python's clean and readable syntax will allow you to learn more and at
a faster pace. You're code will be simpler to write and troubleshoot.

If your target field is data science/engineering, then Python is an
*excellent* language to learn. Devoting time to learning Python
language fundamentals will support your use of the many data science,
machine learning, and modeling packages in widespread use.
