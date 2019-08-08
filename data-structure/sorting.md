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

![](../.gitbook/assets/image%20%286%29.png)

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

![](../.gitbook/assets/image%20%285%29.png)

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

## Quick Sort

## Linear Sorting

## Counting Sort

## Radix Sort

## Bucket Sort

