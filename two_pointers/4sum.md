# 🔶 4Sum – Optimal Approach (Two Pointers)

---

## 🔗 Problem Link

* LeetCode: https://leetcode.com/problems/4sum/

---

## 📌 Problem

Given an array `nums` and an integer `target`, return all **unique quadruplets**:

```text
[nums[i], nums[j], nums[left], nums[right]]
```

such that:

```text
nums[i] + nums[j] + nums[left] + nums[right] = target
```

---

## 🚀 Intuition

* Extension of **3Sum**
* Fix **two elements (`i`, `j`)**
* Use **two pointers (`left`, `right`)** to find remaining two

👉 Goal: Reduce **4 nested loops → 2 loops + 2 pointers**

---

## 🧩 Algorithm

### 🔹 Step 1: Sort the Array

```python id="7d6a8q"
nums.sort()
```

---

### 🔹 Step 2: First Loop (`i`)

```python id="0k8m6s"
for i in range(len(nums)):
```

#### Skip duplicates:

```python id="w5x3jq"
if i > 0 and nums[i] == nums[i - 1]:
    continue
```

---

### 🔹 Step 3: Second Loop (`j`)

```python id="j7m2xk"
for j in range(i + 1, len(nums)):
```

#### Skip duplicates:

```python id="g3l9pz"
if j > i + 1 and nums[j] == nums[j - 1]:
    continue
```

---

### 🔹 Step 4: Two Pointer Setup

```python id="k9v2nb"
left = j + 1
right = len(nums) - 1
```

---

### 🔹 Step 5: Find Quadruplets

```python id="z1p4mc"
while left < right:
    total = nums[i] + nums[j] + nums[left] + nums[right]
```

---

### 🔹 Step 6: Check Conditions

#### ✅ If `total == target`

* Store quadruplet
* Move both pointers

#### ⬆️ If `total < target`

```python id="m2q8ws"
left += 1
```

#### ⬇️ If `total > target`

```python id="r8k3xy"
right -= 1
```

---

### 🔹 Step 7: Skip Duplicates (Critical ⚠️)

```python id="n6f1ab"
# Skip duplicates for left
while left < right and nums[left] == nums[left - 1]:
    left += 1

# Skip duplicates for right
while left < right and nums[right] == nums[right + 1]:
    right -= 1
```

---

## 🧠 Dry Run (ASCII)

```text id="4sumdry"
nums = [1, 0, -1, 0, -2, 2], target = 0

Sorted:
[-2, -1, 0, 0, 1, 2]

Fix:
i = -2
j = -1

left = 0, right = 2

   i     j     left     right
  -2    -1      0         2
   ↓     ↓      ↓         ↓

sum = -2 + (-1) + 0 + 2 = -1 ❌

Move left → continue searching
```

---

## ⚡ Key Insights

* Fix 2 elements → reduce problem to **2Sum**
* Sorting helps:

  * Pointer movement
  * Duplicate removal
* Duplicate handling is **very important**

---

## ⏱️ Complexity

| Type  | Value |
| ----- | ----- |
| Time  | O(n³) |
| Space | O(1)  |

---

## ⚠️ Edge Cases

```text id="4sumedge"
- nums length < 4 → return []
- Large numbers → watch for overflow (in some languages)
```

---

## 🎯 Pattern

* Sorting + Two Pointers
* Extension of:

  * 2Sum → 3Sum → 4Sum

---

## 💡 One-Line Summary

> Fix two elements → use two pointers → adjust sum → skip duplicates → store result

---
