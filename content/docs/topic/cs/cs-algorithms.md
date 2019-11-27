---
title: "Algorithms"
bookHidden: true
---

# Algorithms

## Searching

### Linear Search

#### Introduction

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

### Binary Search

#### Introduction

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

#### Time Complexity

<img src="https://latex.codecogs.com/svg.latex?O(log(n))">

## Sorting

### Selection Sort

Type: in-place

The algorithm sorts an array by repeatedly finding the minimum element (considering ascending order) from unsorted part and putting it at the beginning. The algorithm maintains two sub-array in a given array:

- One that is already sorted
- Remaining unsorted sub-array

**Implementation**

```python
def selection_sot(A):
    for i in range(len(A)):
        min_idx = i
        for j in range(i+1, len(A)):
            if A[min_idx] > A[j]:
                min_idx = j
        A[i], A[min_idx] = A[min_idx], A[i]
    return A
```

**Time Complexity**

<img src="https://latex.codecogs.com/svg.latex?O(n^2)">

**Space Complexity**

<img src="https://latex.codecogs.com/svg.latex?O(1)">

### Bubble Sort

Type: in-place

This algorithm works by repeatedly swapping the adjacent elements if they are in the wrong order.

**Implementation**

*Naive Implementation*

Always <img src="https://latex.codecogs.com/svg.latex?O(n^2)">

```python
def bubbleSort(arr): 
    n = len(arr) 
  
    # Traverse through all array elements 
    for i in range(n): 
  
        # Last i elements are already in place 
        for j in range(0, n-i-1): 
  
            # traverse the array from 0 to n-i-1 
            # Swap if the element found is greater 
            # than the next element 
            if arr[j] > arr[j+1] : 
                arr[j], arr[j+1] = arr[j+1], arr[j] 
```

*Optimized Implementation*

Best cas <img src="https://latex.codecogs.com/svg.latex?O(n)"> when array is already sorted.

```python
def bubbleSort(arr): 
    n = len(arr) 
   
    # Traverse through all array elements 
    for i in range(n): 
        swapped = False
  
        # Last i elements are already 
        #  in place 
        for j in range(0, n-i-1): 
   
            # traverse the array from 0 to 
            # n-i-1. Swap if the element  
            # found is greater than the 
            # next element 
            if arr[j] > arr[j+1] : 
                arr[j], arr[j+1] = arr[j+1], arr[j] 
                swapped = True
  
        # IF no two elements were swapped 
        # by inner loop, then break 
        if swapped == False: 
            break
```

*Recursive Implementation*

This implementation variant offers no performance/implementation improvements or advantages.

Idea:

- Base Case: Return if array size is 1
- Do one pass of normal Bubble Sort, fixing the last element of the current sub-array
- Recur for all elements except the last of current sub-array.

```python
def bubble_sort_recursive(arr): 
    for i, num in enumerate(arr): 
        try: 
            if arr[i+1] < num: 
                arr[i] = arr[i+1] 
                arr[i+1] = num 
                bubble_sort(arr) 
        except IndexError: 
            pass
    return arr 
```

**Time Complexity**

Depends (see each implementation).

**Space Complexity**

<img src="https://latex.codecogs.com/svg.latex? O(1)">

### Insertion Sort

Type: in-place

An algorithm that works similarly to the way playing cards are sorted.

**Implementation**

```python
def insertionSort(arr): 
  
    # Traverse through 1 to len(arr) 
    for i in range(1, len(arr)): 
  
        key = arr[i] 
  
        # Move elements of arr[0..i-1], that are 
        # greater than key, to one position ahead 
        # of their current position 
        j = i-1
        while j >= 0 and key < arr[j] : 
                arr[j + 1] = arr[j] 
                j -= 1
        arr[j + 1] = key 
```

**Time Complexity**
<img src="https://latex.codecogs.com/svg.latex?O(n^2)">

**Space Complexity**
<img src="https://latex.codecogs.com/svg.latex?O(1)">