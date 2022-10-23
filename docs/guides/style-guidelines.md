## Style Notes for Type Literals
PEP8 guidelines make several recommendations that apply to many of the types covered 
here.  The following examples demonstrate how to follow these widely accepted guidelines. 

### String Delimiters
In Python, single and double quotes are equivalent. PEP8 makes no recommendation as to 
which one to use for string delimiters.  Decide which one you prefer and use it 
consistently throughout a single codebase.
```py
# WRONG:
first_name = "Jack"
last_name = 'Handy'    # mixed quote types for strings
```

```py
# CORRECT:
first_name = 'Jack'
last_name = 'Handy'    # pick one type and use it consistently
```

### Sequences
Sequences of values or variables are used when defining lists, tuples, dictionaries, and 
sets. PEP8 makes a general recommendation that a space be included after *any* comma 
that is not at the end of a line. When defining these types, include these spaces.

The following examples demonstrate:

```py
# WRONG:
nums = [1,2,3]
```

```py
# CORRECT:
nums = [1, 2, 3]
```

```py
# WRONG:
codes_countries = {'US': 'United States','IN': 'India'}
```

```py
# CORRECT:
codes_countries = {'US': 'United States', 'IN': 'India'}
```

```py
# WRONG:
woody_plants = {'tree','shrub','bush','hedge'}
```

```py
# CORRECT:
woody_plants = {'tree', 'shrub', 'bush', 'hedge'}
```

### Spaces After `:`
When defining dictionaries, include a single space after every semicolon `:`.

```py
# WRONG:
codes_countries = {'US':'United States', 'IN':'India'}
```

```py
# CORRECT:
codes_countries = {'US': 'United States', 'IN': 'India'}
```