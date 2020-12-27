# Sorting

* \*\*\*\*[**Comparison Sorting**](sorting.md#comparison-sorting)\*\*\*\*
  * [Selection Sort](sorting.md#selection-sort)
  * [Bubble Sort](sorting.md#bubble-sort)
  * [Insertion Sort ](sorting.md#insertion-sort)
  * [Merge Sort](sorting.md#merge-sort)
  * [Heap Sort](sorting.md#heap-sort)
  * [Quick Sort](sorting.md#quick-sort)
* \*\*\*\*[**Linear Sorting**](sorting.md#linear-sorting)\*\*\*\*
  * [Counting Sort](sorting.md#counting-sort)
  * [Radix Sort](sorting.md#radix-sort)
  * [Bucket Sort](sorting.md#bucket-sort)

## Comparison Sorting

![](../.gitbook/assets/image%20%287%29.png)

|  | Selection Sort | Bubble Sort | Insertion Sort | Merge Sort | Heap Sort | Quick Sort |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Best | O\(n^2\) | O\(n\) | O\(n\) | O\(n log n\) | O\(n log n\) | O\(n log n\) |
| Average  | O\(n^2\) | O\(n^2\) | O\(n^2\) | O\(n log n\) | O\(n log n\) | O\(n log n\) |
| Worst | O\(n^2\) | O\(n^2\) | O\(n^2\) | O\(n log n\) | O\(n log n\) | O\(n^2\) |
| Worst\(space\) | O\(1\) | O\(1\) | O\(1\) | O\(n\) | O\(1\) | O\(log n\) |

## Selection Sort

![](../.gitbook/assets/image%20%281%29.png)

1. Find the **smallest** element in **array\[1,...,n\]** and swap into index **0**;  每一次从后面找最小的数，放到当前index里。
2. Find the **smallest** element in **array\[2,...,n\]** and swap into index **1**;
3. **Keep going** until all elements are sorted. 

**Time Complexity:** 

* Best: O\(n^2\)
* Worst: O\(n^2\)

```python
def selectionSort(nums): 
    for i in range(len(nums)): 
        minIdx = i; # assume [i] contain the min value
        for j in range(i+1, len(nums)): 
            if nums[j] < nums[minIdx]: #find min value from [i+1,...,n]
                minIdx = j;
        nums[minIdx], nums[i] = nums[i], nums[minIdx];
```

## Bubble Sort

![](../.gitbook/assets/image%20%282%29.png)

1. Go through all elements, compare it with the one after it.If current index has greater value, swap. 每次和后一个数对比，如果大，就交换。每次把最大的数放后面。
2. Repeats until all elements are sorted. 

**Time complexity:** 

* Best: O\(n\) - if nearly sorted
* Worst: O\(n^2\)

```python
def bubbleSort(nums):
    for i in range(len(nums)-1, 0, -1): 
        swap = 0
        for j in range(len(nums)):
            if nums[j] > nums[j+1]:
                nums[j], nums[j+1] = nums[j+1], nums[j]
                count += 1
        if swap == 0: #if array is sorted
            break
```

## Insertion Sort

![](../.gitbook/assets/image%20%284%29.png)

* Go through all elements, compare it with the one before it, keep going until it's larger or first of array.  每次往前比较，直到它比前面的数字都大或者前面没数字了。

```python
def insertionSort(nums):
    for i in range(nums):
        j = i
        while(j > 0 and nums[j] < nums[j-1]):
            nums[j],nums[j-1] = nums[j-1], nums[j]
```

## Merge Sort

![](../.gitbook/assets/image%20%286%29.png)

1. **Divide**: split partition into two sequence, about `n/2` elements each
2. **Conquer**: merge two sorted subsequences into a **sorted** sequence

**Complexity:** 

* Time complexity: O\(n log n\)
* Space complexity: O\(n\) – store partitions for merge

```python
def mergeSort(A, l, r):
    m = (m + r) // 2
    mergeSort(A, l, m)
    mergeSort(A, m+1, r)
    merge(A, l, m, r)
    
def merge(A, l, m, r):
    n1, n2 = m-l+1, r-m
    left, right = [0]*n1, [0]*n2 #create tmp arrays
    for i in range(n1):
        left[i] = A[l+i]
    for j in range(n2):
        right[j] = A[m+j+1]
        
    #merge temp arrays back into A
    i, j, k = 0, 0, 1
    while(i < n1 and j < n2):
        if left[i] <= right[j]:
            A[k] = left[i]
            i += 1
        else: 
            A[k] = right[j]
            j += 1
        k += 1
    while(i< n1): #copy remain elements in left
        A[k] = left[i]
        i += 1 
        k += 1
    while(j < n2): #copy remain elements in right
        A[k] = right[j]
        j += 1
        k += 1
```

## Heap Sort

![](../.gitbook/assets/image%20%288%29%20%281%29.png)

1. Build a internal max/min heap
2. For every node from leaf to root, swap with current root, check if it's violates the max/min heap property, if does, perform heapify. 

Time complexity: O\(n log n\)

```python
def heapSort(A):
    buildHeap(A) 
    i = len(A)
    while(i > 1): # i -> n to 2
        A[1], A[i] = A[i], A[1] #make new element as root
        n -= 1
        heapify(A, 1) # down heap
        
def buildHeap(A): #build max heap
    i = len(A) // 2
    while(i > 0): # n//2 to 1
        heapify(A, i) # only heapify internal nodes here
        i -= 1
        
def heapify(A, i): 
    n = len(A)
    while(i < n):
        l = 2 * i
        r = 2 * i + 1
        largest = l if l < n and A[i] < A[l] else i
        if r < n and A[r] > A[largest]:
            largest = r
        if i == largest:
            break
        A[i], A[largest] = A[largest],A[i]
        i = largest
    
```

## Quick Sort

1. Select a pivot, usually **first** or **last** element in the array
2. **Divide**: partition array into 2 subarrays s.t. elements in the lower part &lt;= elements in the higher part. 
3. **Conquer**: recursively sort the 2 subarrays

Time complexity: O\(n log n\) – almost in-place

```python

```

## Linear Sorting

## Counting Sort

## Radix Sort

## Bucket Sort

