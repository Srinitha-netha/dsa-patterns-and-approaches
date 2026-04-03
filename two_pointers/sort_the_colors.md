# 🔶 Sort Colors – Optimal Approach (Dutch National Flag Algorithm)

---

## 🔗 Problem Link
[Sort Colors - LeetCode](https://leetcode.com/problems/sort-colors/)


## 📌 Problem

Given an array `nums` containing only `0`, `1`, and `2`, sort the array **in-place** such that:

```text id="sc1"
0 → red, 1 → white, 2 → blue
```

---

## 🚀 Intuition

* We need to group:

  * `0`s → left side
  * `1`s → middle
  * `2`s → right side

👉 Use **three pointers** to partition the array in a single pass

---

## 🧠 Core Idea (3 Pointers)

```text id="sc2"
[ 0's | 1's | unknown | 2's ]
   ↑      ↑       ↑       ↑
  low    mid            high
```

* `low` → position for next `0`
* `mid` → current element
* `high` → position for next `2`

---

## ⚙️ 3-Pointer Algorithm (Step-by-Step)

```text
1. Initialize:
   low = 0, mid = 0, high = n - 1

2. While mid <= high:

   a) If nums[mid] == 0:
      swap(nums[low], nums[mid])
      low++
      mid++

   b) Else if nums[mid] == 1:
      mid++

   c) Else (nums[mid] == 2):
      swap(nums[mid], nums[high])
      high--
      (Do NOT increment mid)

3. End loop → array is sorted
```


## 🧩 Algorithm

### 🔹 Step 1: Initialize Pointers

```python id="sc3"
low = 0
mid = 0
high = len(nums) - 1
```

---

### 🔹 Step 2: Traverse the Array

```python id="sc4"
while mid <= high:
```

---

### 🔹 Step 3: Handle Cases

#### 🟢 Case 1: nums[mid] == 0

```python id="sc5"
swap(nums[low], nums[mid])
low += 1
mid += 1
```

👉 Place `0` in correct position

---

#### ⚪ Case 2: nums[mid] == 1

```python id="sc6"
mid += 1
```

👉 Already in correct position

---

#### 🔴 Case 3: nums[mid] == 2

```python id="sc7"
swap(nums[mid], nums[high])
high -= 1
```

👉 Move `2` to the end
👉 **Do NOT increment mid here** (important ⚠️)

---

## 🧠 Dry Run (ASCII)

```text id="sc8"
nums = [2, 0, 2, 1, 1, 0]

Initial:
low=0, mid=0, high=5

Step:
nums[mid]=2 → swap(mid, high)

[0, 0, 2, 1, 1, 2]
 ↑     ↑        ↑
low   mid     high

Continue...
```

---

## ⚡ Key Insights

* Single pass solution (**O(n)**)
* No extra space (**in-place sorting**)
* Key trick:

```text id="sc9"
When swapping with high → DO NOT move mid
```

---

## ⏱️ Complexity

| Type  | Value |
| ----- | ----- |
| Time  | O(n)  |
| Space | O(1)  |

---

## ⚠️ Edge Cases

```text id="sc10"
- All elements same → already sorted
- Empty array → no operation
```

---

## 🎯 Pattern

* Dutch National Flag Algorithm
* Three Pointers
* Partitioning

---

## 💡 One-Line Summary

> Use low, mid, high pointers to partition array into 0s, 1s, and 2s in one pass

---
