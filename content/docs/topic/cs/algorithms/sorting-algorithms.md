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

Also a divide-and-conquer algorithm. It picks an element as pivot and partitions the given array around the picked pivot.

Some of the different ways of pivoting:

- Always pick the first element as the pivot
- Always pick the last element as the pivot
- Pick random element as the pivot
- Pick median as the pivot

The core of quick-sort is the partition() function. Target of partitions is, given an array and an element x of array as pivot, put x at its correct position in sorted array and put all smaller elements (smaller than x) before x, and put all greater elements (greater than x) after x. All of these should be done in linear time.

### Implementation

```py
def partition(arr,low,high): 
    i = ( low-1 )         # index of smaller element 
    pivot = arr[high]     # pivot 
  
    for j in range(low , high): 
  
        # If current element is smaller than the pivot 
        if   arr[j] < pivot: 
          
            # increment index of smaller element 
            i = i+1 
            arr[i],arr[j] = arr[j],arr[i] 
  
    arr[i+1],arr[high] = arr[high],arr[i+1] 
    return ( i+1 ) 
  
# The main function that implements QuickSort 
# arr[] --> Array to be sorted, 
# low  --> Starting index, 
# high  --> Ending index 
  
# Function to do Quick sort 
def quickSort(arr,low,high): 
    if low < high: 
  
        # pi is partitioning index, arr[p] is now 
        # at right place 
        pi = partition(arr,low,high) 
  
        # Separately sort elements before 
        # partition and after partition 
        quickSort(arr, low, pi-1) 
        quickSort(arr, pi+1, high) 
  
```

**Time Complexity**

Worst Case: <img src="https://latex.codecogs.com/svg.latex?O(n^2)">

Occurs when the partition process always picks greatest or smallest element as pivot.

Best Case: <img src="https://latex.codecogs.com/svg.latex?O(n*log(n))">

Occurs when the partition process always picks the middle element as pivot.

### Notes

Quick-sort is preferred over merge-sort for arrays as it is in-place and does not require extra memory.

Merge-sort is preferred over quick-sort for linked list. Unlike arrays, linked list nodes may not be adjacent in memory. Unlike array, in linked list, we can insert items in the middle in O(1) extra space and O(1) time. Therefore merge operation of merge sort can be implemented without extra space for linked lists.

## Heap Sort

A comparison-based sorting technique based on the Binary Heap data structure.

### Binary Heap

type: in-place

[(Main Article)]

A complete binary tree is a binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible.

A Binary Heap is a Complete Binary Tree where items are stored in a special order such that value in a parent node is greater(or smaller) than the values in its two children nodes. The former is called as max heap and the latter is called min heap.

We represent Binary Heap as an array it, being a Complete Binary Tree, can be easily represented as array and array based representation is space efficient. If the parent node is stored at index I, the left child can be calculated by 2 * I + 1 and right child by 2 * I + 2.

### Methdology

- Build a max heap from input data
- Replace the largest element (at the root) with the last item of the heap followed by reducing the size of heap by 1. Finally, heapify the root of tree
- Repeat the above steps while size of heap is greater than 1


```py
# To heapify subtree rooted at index i. 
# n is size of heap 
def heapify(arr, n, i): 
    largest = i # Initialize largest as root 
    l = 2 * i + 1     # left = 2*i + 1 
    r = 2 * i + 2     # right = 2*i + 2 
  
    # See if left child of root exists and is 
    # greater than root 
    if l < n and arr[i] < arr[l]: 
        largest = l 
  
    # See if right child of root exists and is 
    # greater than root 
    if r < n and arr[largest] < arr[r]: 
        largest = r 
  
    # Change root, if needed 
    if largest != i: 
        arr[i],arr[largest] = arr[largest],arr[i] # swap 
  
        # Heapify the root. 
        heapify(arr, n, largest) 
  
# The main function to sort an array of given size 
def heapSort(arr): 
    n = len(arr) 
  
    # Build a maxheap. 
    for i in range(n, -1, -1): 
        heapify(arr, n, i) 
  
    # One by one extract elements 
    for i in range(n-1, 0, -1): 
        arr[i], arr[0] = arr[0], arr[i] # swap 
        heapify(arr, i, 0)
```

**Time Complexity** 

Heapify: <img src="https://latex.codecogs.com/svg.latex?O(log(n))">

createAndBuildHeap: is <img src="https://latex.codecogs.com/svg.latex?O(n)">

Overall: <img src="https://latex.codecogs.com/svg.latex?O(n(log(n)))">