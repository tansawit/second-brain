---
title: "Sorting Algorithms"
---

# Sorting Algorithms

## Selection Sort

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

## Bubble Sort

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

## Insertion Sort

Type: in-place

An algorithm that works similarly to the way playing cards are sorted.

**Implementation**

*Standard Implementation*

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

*Recursive Implementation*

Idea:

- Base Case: If array size is 1 or smaller, return.
- Recursively sort the first n-1 elements
- Insert last element at its correct position in sorted array

```python
def insertion_sort_recursive(arr,n): 
    # base case 
    if n<=1: 
        return
      
    # Sort first n-1 elements 
    insertionSortRecursive(arr,n-1) 
    '''Insert last element at its correct position 
        in sorted array.'''
    last = arr[n-1] 
    j = n-2
      
      # Move elements of arr[0..i-1], that are 
      # greater than key, to one position ahead 
      # of their current position  
    while (j>=0 and arr[j]>last): 
        arr[j+1] = arr[j] 
        j = j-1
  
    arr[j+1]=last
```

**Time Complexity**
<img src="https://latex.codecogs.com/svg.latex?O(n^2)">

**Space Complexity**
<img src="https://latex.codecogs.com/svg.latex?O(1)">

## Merge Sort

Type: not in-place

A divide-and-conquer sorting algorithm. It divides input into two haves, call itself on the two halves, then merges the two sorted halves. 

The merge(arr, l, m, r) is the key process that assumes that arr[l..m]and arr[m+1..r] are sorted and merge the two sorted sub-array.

**Implmentation**
```python
def mergeSort(arr): 
    if len(arr) >1: 
        mid = len(arr)//2 #Finding the mid of the array 
        L = arr[:mid] # Dividing the array elements  
        R = arr[mid:] # into 2 halves 
  
        mergeSort(L) # Sorting the first half 
        mergeSort(R) # Sorting the second half 
  
        i = j = k = 0
          
        # Copy data to temp arrays L[] and R[] 
        while i < len(L) and j < len(R): 
            if L[i] < R[j]: 
                arr[k] = L[i] 
                i+=1
            else: 
                arr[k] = R[j] 
                j+=1
            k+=1
          
        # Checking if any element was left 
        while i < len(L): 
            arr[k] = L[i] 
            i+=1
            k+=1
          
        while j < len(R): 
            arr[k] = R[j] 
            j+=1
            k+=1
```

**Time Complexity**
<img src="https://latex.codecogs.com/svg.latex?O(nlogn)">

**Space Complexity**
<img src="https://latex.codecogs.com/svg.latex?O(n)">

## Quick Sort