# 🔶 3Sum Closest – Optimal Approach (Two Pointers)

---

## 📌 Problem

Given an array `nums` and an integer `target`, find the **sum of three integers** such that the sum is **closest to target**.

Return the **closest sum**.

---

## 🚀 Intuition

* Similar to **3Sum**, but instead of finding exact `0`
* We minimize:

```id="c1"
|current_sum - target|
```

👉 Goal = **closest value, not exact match**

---

## 🧩 Algorithm

### 🔹 Step 1: Sort the Array

```python
nums.sort()
```

---

### 🔹 Step 2: Initialize Result

```python
res = nums[0] + nums[1] + nums[2]
```

---

### 🔹 Step 3: Fix One Element

```python
for i in range(len(nums)):
```

---

### 🔹 Step 4: Two Pointers Setup

```python
left = i + 1
right = len(nums) - 1
```

---

### 🔹 Step 5: Traverse Using Two Pointers

```python
while left < right:
    current = nums[i] + nums[left] + nums[right]
```

---

### 🔹 Step 6: Update Closest Sum

```python
if abs(current - target) < abs(res - target):
    res = current
```

---

### 🔹 Step 7: Move Pointers

#### ⬆️ If current < target

```python
left += 1
```

#### ⬇️ If current > target

```python
right -= 1
```

#### ✅ If exact match

```python
return current
```

---

## 🧠 Dry Run (ASCII)

```text
nums = [-1, 2, 1, -4], target = 1

Sorted:
[-4, -1, 1, 2]

Try:
-4 + -1 + 2 = -3
Closest so far = -3

Move pointers → improve towards target
```

---

## ⚡ Key Differences from 3Sum

| 3Sum            | 3Sum Closest               |
| --------------- | -------------------------- |
| Find exact 0    | Find closest to target     |
| Skip duplicates | No need to skip duplicates |
| Store triplets  | Store single sum           |

---

## ⏱️ Complexity

| Type  | Value |
| ----- | ----- |
| Time  | O(n²) |
| Space | O(1)  |

---

## ⚠️ Edge Cases

```text
- Array size < 3 → not valid
- Negative + positive mix → important for closest
```

---

## 💡 One-Line Summary

> Fix one element → use two pointers → update closest sum → move towards target

---
