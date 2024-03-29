---
title: "Searching Algorithms"
---

# Searching

## Linear Search

### Introduction

The algorithm of choice for short lists as it is simple and requires minimal coding. It simply iterates through the list, checking if each element is the target.If the targeted element is found, the algorithm finishes.

However, it is rarely used in practice as other algorithms allow for significantly faster speed compared to it.

**Implementation**

```python
def linear_search(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1
```

**Time Complexity**

<img src="https://latex.codecogs.com/svg.latex?O(n)">

## Binary Search

### Introduction

The Binary Search is one of the most widely used algoirthms. The algorithms works on an ordered collection of elements.

The algorithm starts at the middle of the database. If the target number is greater than the middle number, the search will continue with the upper half of the database, else it will continue with the lower half. It continues this process, cutting the data in half until it finds the target record

3 main sections:

- Pre-processing - Sort collection (if needed)
- Binary Search - Use loop or recursion to divide the current search space in half after each comparison
- Post-processing - Determine viable candidates in the remaining space

**Implementation**

```python
def binary_search(arr, l, r, x):
    # Base case
    if r >= 1:
        mid = l + (r - 1) / 2

        # If element is present at the middle
        if arr[mid] == x:
            return mid

        # If element is smaller than mid, check left-array
        elif arr[mid] > x:
            return binary_search(arr, l, mid-1, x)
        
        # Else the element can only be present in the right-array
        else:
            return binary_search(arr, mid+1, r, x)
     
     else:
        # Element is not present in array
        return -1
```

### Time Complexity

<img src="https://latex.codecogs.com/svg.latex?O(log(n))">

