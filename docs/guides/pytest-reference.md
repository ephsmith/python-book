## Introduction
Pytest is an open source, third-party test runner for Python. It is arguably the 
simplest test runner available for Python.  There is a _lot_ that could be written 
about `pytest` and this reference does not attempt full coverage of the topic.  The 
purpose of this reference is to provide students with a quick reference to useful 
`pytest` tips and command examples. 

## Installing Pytest
Installation is "automatic" for those of you that are using PyCharm to work on your 
projects.  PyCharm will prompt you to install the packages listed in the `requirements.
txt` file within your assignment repository.

!!! info
    Python projects often use a file named `requirements.txt` to list project 
    dependencies.  Dependencies are other Python packages must be installed in order 
    for the target application to run properly. `requirements.txt` files include a 
    list of package names along with a minimum (or specific) required version. The 
    Python package installer `pip` provides a way to easily install these packages.

!!! tip
    If you are using Pytest within PyCharm, you can skip the commandline.  PyCharm 
    provides GUI elements to run and view results of tests.
    **Right-click on the `tests` directory and choose "Run Tests in tests".**

If you would like to install `pytest` in your main Python installation, you can run 
the following at the command prompt:

=== "Windows"
    ```con
    PS> python -m pip install pytest
    ```

=== "Linux/macOS"
    ```con
    $ python3 -m pip install pytest
    ```

## Useful `pytest` Command Variations
In the context of this course, any of these commands should work when run from the 
command line at the *root of your repository*.  

!!! note
    PyCharm provides the *Terminal* tab at the bottom of the main window.  This will 
    launch a terminal session at the root of your repository.  If you are on Windows, 
    this defaults to a Powershell (PS) term.  On macOS, the default is a ZSH term; on 
    Linux this is likely a BaSH terminal.

### Run all Tests
If you want to run all tests on your code, run the following command:

```shell
pytest
```

### Filter Tests
A typical professional Python project will include hundreds (or more) tests. It 
is often desirable to filter these tests.  Pytest makes this possible with the 
filter command option `-k`.  Use the command `pytest -k <filter_text>` where 
`<filter_text>` is a string of text that `pytest` will use to match test cases.  Test 
cases are typically the functions contained in modules under the `tests` directory.  

Consider the following project structure:

```
.
├── demo_pytest
│   ├── __init__.py
│   └── clean.py
└── tests
    ├── __init__.py
    └── test_clean.py
```

The `clean.py` module has the following simple contents. Note that there are just two 
functions contained in this module.  

```py title="clean.py"
"""
clean.py contains utility functions for cleaning text.
"""

def clean_spaces(text):
    """
    Removes spaces from the input text.

    Parameters
    ----------
    text the text to be cleaned.

    Returns
    -------
    the text with all spaces removed.
    """
    return text.replace(' ', '')


def clean_underscores(text):
    """
    Removes underscores from the input text.

    Parameters
    ----------
    text the text to be cleaned.

    Returns
    -------
    the text with all underscores removed.
    """
    return text.replace('_', '')
```

The `tests/test_clean.py` module contains functions that test functions in the clean 
module. Note that there are multiple test functions here for the `clean_spaces()` 
function and just one test function for the `clean_underscores()` function. Each of 
the functions in the `test_clean.py` module are test cases.   

```python title="test_clean.py"
from demo_pytest.clean import clean_spaces, clean_underscores


def test___clean_spaces___removes_leading_space():
    input_, expected = " Hello", "Hello"
    assert clean_spaces(input_) == expected


def test___clean_spaces___removes_trailing_spaces():
    input_, expected = "Hello ", "Hello"
    assert clean_spaces(input_) == expected


def test___clean_spaces___removes_bounded_spaces():
    input_, expected = "Hello There", "HelloThere"
    assert clean_spaces(input_) == expected


def test___clean_underscores___removes_all_underscores():
    input_, expected = "_Hello_There_You_", "HelloThereYou"
    assert clean_underscores(input_) == expected
```

Pytest will only run tests for `clean_spaces()` if we use `clean_spaces` as the filter 
text:

```shell
pytest -k "clean_spaces"
```

Similarly, the following command runs only those test cases that contain the text 
`clean_underscores` in the function name:

```shell
pytest -k "clean_underscores"
```

### Class Specific Examples
All assignments in this course include a `src` directory and a `tests` directory. 
Solutions are implemented in the modules included in the `src` directory and tests are 
located in the `tests` directory. 

To run all tests using `pytest`, run the `pytest` command with no arguments from the 
directory that contains the `src` and `tests` directories.  This produce a *lot* of 
output along with a short test summary at the end for tests that failed.  

``` title="pytest short test summary"
================= short test summary info ==================
FAILED tests/test_ex_0_4.py::test___int_sum___returns_correct_value[2-3] - AttributeError: module 'src.ex_0_4' has no attribute 'i...
FAILED tests/test_ex_0_4.py::test___int_sum___returns_correct_value[3-6] - AttributeError: module 'src.ex_0_4' has no attribute 'i...
FAILED tests/test_ex_0_4.py::test___int_sum___returns_correct_value[4-10] - AttributeError: module 'src.ex_0_4' has no attribute 'i...
FAILED tests/test_ex_0_4.py::test___int_sum___returns_correct_value[5-15] - AttributeError: module 'src.ex_0_4' has no attribute 'i...
FAILED tests/test_ex_0_4.py::test___odd_sum___returns_correct_value[2-4] - AttributeError: module 'src.ex_0_4' has no attribute 'o...
FAILED tests/test_ex_0_4.py::test___odd_sum___returns_correct_value[3-9] - AttributeError: module 'src.ex_0_4' has no attribute 'o...
FAILED tests/test_ex_0_4.py::test___odd_sum___returns_correct_value[4-16] - AttributeError: module 'src.ex_0_4' has no attribute 'o...
FAILED tests/test_ex_0_4.py::test___odd_sum___returns_correct_value[5-25] - AttributeError: module 'src.ex_0_4' has no attribute 'o...
FAILED tests/test_ex_0_5.py::test___ground_cover___exists[SN00-0] - AttributeError: module 'src.ex_0_5' has no attribute 'g...
FAILED tests/test_ex_0_5.py::test___ground_cover___exists[SN10-1] - AttributeError: module 'src.ex_0_5' has no attribute 'g...
FAILED tests/test_ex_0_5.py::test___ground_cover___exists[SN20-2] - AttributeError: module 'src.ex_0_5' has no attribute 'g...
FAILED tests/test_ex_0_5.py::test___depth___exists[SN00-0] - AttributeError: module 'src.ex_0_5' has no attribute 'd...
FAILED tests/test_ex_0_5.py::test___depth___exists[SN11-1] - AttributeError: module 'src.ex_0_5' has no attribute 'd...
FAILED tests/test_ex_0_5.py::test___depth___exists[SN22-2] - AttributeError: module 'src.ex_0_5' has no attribute 'd...
```
Note that each test case has the name pattern `test___<function>___<case>`.  Here, 
`<function>` is the name of the function under test and `<case>` is the expected 
outcome for the test case.

We can filter pytest tests based on the `<function>` portion of any of these tests.  
To run tests only for `int_sum` for instance, use the following command 

```shell title="Run tests for int_sum"
pytest -k "int_sum"
```
