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

Time complexity: 

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

## Merge Sort

![](../.gitbook/assets/image%20%285%29.png)

## Heap Sort

## Quick Sort

## Linear Sorting

## Counting Sort

## Radix Sort

## Bucket Sort

