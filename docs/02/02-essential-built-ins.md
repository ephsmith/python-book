## Introduction
Another important topic in the entries of a high-level survey of the Python language 
are built-in functions.  Built-in functions are functions that are available to your 
Python without the import statements. Each of the following subsections provides a 
brief overview of the function covered. Some of these have been introduced in 
other sections of the text but are listed here for the sake of quick access and simple 
reference.

### `enumerate()`
Pass any iterable to the `enumerate()` function, and it will return a lazy sequence of 
tuples containing a *count* (staring at 0) and values returned from iterating over the 
iterable. Note that `enumerate()` iterates *lazily* (only as needed) instead of 
returning all elements of the sequence. This is not typically a problem because 
enumerate is widely used when iterating over the target sequence passed to it. 

```py title="enumerate_example.py"
country_codes = ['IN', 'NL', 'US']

for count, code in enumerate(country_codes):
    print(count, code)
```

Running `enumerate_example.py` produces the following output in the Python shell.

```pycon title="enumerate_example.py output"
0 IN
1 NL
2 US
```

We can coerce `enumerate()` into returning all items in the sequence by passing it to 
`list` or `tuple`. 

```pycon
>>> # force enumerate to return all items
>>> list(enumerate(country_codes))
[(0, 'IN'), (1, 'NL'), (2, 'US')]   # a list of tuples is returned.
```


!!! tip
    A great use case for enumerate is when looping over an iterable of unknown size. 
    This may sound strange at first. File reading is a classic example of this. If we 
    want to keep an index of each line in a file as we read the file, we can use 
    `enumerate()`.  


### `len()`
Pass any container to the `len()` function, and it will return the number of items 
stored in the container. A container is any type in Python that stores an arbitrary 
number of items.  This includes `list`, `tuple`, `set`, `dict`, `str` and more.  An 
example may be required for use on `dict` types. 

```py
>>> codes_countries = {'US': 'United States', 'IN': 'India'}
>>> len(code_countries)
2                        # (1)!
```

1. `len()` returns the number of keys when called on a `dict` type.

