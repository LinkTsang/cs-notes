- [Search](#search)
  - [Binary Search](#binary-search)
    - [Python](#python)
- [Tree](#tree)
- [String](#string)
- [Sort](#sort)
  - [Quick Sort](#quick-sort)
  - [Heap Sort](#heap-sort)
  - [Bubble Sort](#bubble-sort)
  - [Insert Sort](#insert-sort)
- [Bit manipulate/tricks](#bit-manipulatetricks)
- [DFS](#dfs)
  - [backtracking](#backtracking)
- [BFS](#bfs)
  - [branch and bound method](#branch-and-bound-method)
- [Divide and Conquer](#divide-and-conquer)
- [DP](#dp)
- [Greedy Algorithm](#greedy-algorithm)

# Search

## Binary Search

- `lower_bound(x) <= x < upper_bound(x)`
- `lower_bound(x) - 1 < x <= upper_bound(x) - 1`
- `equal_range(x) => [lower_bound(x), upper_bound(x))`

### Python

```python
def lower_bound(arr, begin, end, target):
  while begin < end:
    mid = begin + (end - begin) // 2   # avoid overflow, although Python does not need.
    if arr[mid] < target:
      begin = mid + 1
    else:
      end = mid
  return begin


def upper_bound(arr, begin, end, target):
  while begin < end:
    mid = begin + (end - begin) // 2
    if arr[mid] <= target:               # here
      begin = mid + 1
    else:
      end = mid
  return begin


def equal_range(arr, begin, end, target):
  return (lower_bound(arr, begin, end, target),
          upper_bound(arr, begin, end, target))


def binary_search(arr, begin, end, target):
  begin = lower_bound(arr, begin, end, target)
  return begin != end and target == arr[begin]
```

# Tree

# String

# Sort

## Quick Sort


## Heap Sort


## Bubble Sort


## Insert Sort


# Bit manipulate/tricks
```c
// 去掉从右到左的第一个 1
// 可用于统计二进制表示中 1 的个数
x = x & (x - 1)

// 保留最后一位 1
x = x & -x

// 二进制表示逆序
a = ((a & 0xAAAA) >> 1) | ((a & 0x5555) << 1);
a = ((a & 0xCCCC) >> 2) | ((a & 0x3333) << 2);
a = ((a & 0xF0F0) >> 4) | ((a & 0x0F0F) << 4);
a = ((a & 0xFF00) >> 8) | ((a & 0x00FF) << 8);
```
# DFS
## backtracking


# BFS
## branch and bound method

# Divide and Conquer

# DP

# Greedy Algorithm
