---
title: "Python"
bookToC: 2
bookCollapseSection: true
---

# Python

## Basics

- High-level, interpreted language
- Dynamically typed

## Functions

### Features

Can assign variables to function, which can then be passed onto other functions

### Default Values
```python
def add_number(x, y, z=None)    # z is the optional/default value
    if (x == None):
        return x + y
    else:
        return x + y + z
    return sum
```

## Data Structures

### Tuples

Immutable, iterable and mixed-type sequence of variables

```python
x = (1, 'a', 2, 'b')
```

### List

Mutable, iterable, and mixed-type sequence of variables
```
y = [1, 'a', 2, 'b']
```
## Techniques

### Lambda Functions

```python
my_function = lambda a, b, c : a + b
my_function(1, 2, 3) # returns 3
```

### List Comprehension

my_list = [number for number in range(0, 1000) if number % 2 == 0]

### Unpacking

```python
x = ('Sawit', 'Trisirisatayawong', 'sawit.tr@gmail.com')
first_name, last_name, email = x
```
### map()

```python
store1 = [10.00, 11.00, 12.00, 13.00]
store2 = [15.00, 9.00, 8.32, 3.14]
cheapest = map(min, store1, store2)
```

## Libraries

- [datetime]({{<relref "/docs/topic/programming-languages/python/libraries/datetime.md">}}): working with date, time, and durration
- [numpy]({{<relref "/docs/topic/programming-languages/python/libraries/numpy.md">}}): add support for multi-dimensional arrays and linear algebra


## Related Pages

- [Business Intelligence]({{<relref "/docs/topic/business/business-intelligence">}})