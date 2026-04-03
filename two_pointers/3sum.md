# 🔶 3Sum – Optimal Approach (Two Pointers)

---

## 📌 Problem

Given an integer array `nums`, return all **unique triplets** such that:

```id="eq1"
nums[i] + nums[left] + nums[right] = 0
```

---

## 🚀 Intuition (VERY IMPORTANT)

* After **sorting**, the array becomes ordered
* This allows:

  * Moving `left →` increases sum
  * Moving `right ←` decreases sum

👉 So we can efficiently find pairs using **two pointers**

---

## 🧩 Algorithm

### 🔹 Step 1: Sort the Array

```python id="eq2"
nums.sort()
```

---

### 🔹 Step 2: Fix One Element (`i`)

* Loop through array
* Treat `nums[i]` as first element

```python id="eq3"
for i in range(len(nums)):
```

---

### 🔹 Step 3: Skip Duplicates for `i`

```python id="eq4"
if i > 0 and nums[i] == nums[i - 1]:
    continue
```

---

### 🔹 Step 4: Two Pointer Setup

```python id="eq5"
left = i + 1
right = len(nums) - 1
```

---

### 🔹 Step 5: Find Valid Triplets

```python id="eq6"
while left < right:
    total = nums[i] + nums[left] + nums[right]
```

---

### 🔹 Step 6: Pointer Movement

#### ✅ If `total == 0`

* Store triplet
* Move both pointers

#### ⬆️ If `total < 0`

```python id="eq7"
left += 1
```

#### ⬇️ If `total > 0`

```python id="eq8"
right -= 1
```

---

### 🔹 Step 7: Skip Duplicates (Critical ⚠️)

```python id="eq9"
# Skip duplicates for left
while left < right and nums[left] == nums[left - 1]:
    left += 1

# Skip duplicates for right
while left < right and nums[right] == nums[right + 1]:
    right -= 1
```

---

## 🧠 Dry Run (ASCII Visualization)

```id="eq10"
nums = [-1, 0, 1, 2, -1, -4]

Sorted:
[-4, -1, -1, 0, 1, 2]

i = -1
left = -1, right = 2

   i      left       right
  -1       -1          2
   ↓        ↓          ↓

sum = -1 + (-1) + 2 = 0 ✅

Triplet found: [-1, -1, 2]
```

---

## ⚡ Key Insights

* Sorting enables **two-pointer optimization**
* Duplicate skipping ensures **unique triplets**
* Core idea = **Fix one + find pair**

---

## ⏱️ Complexity

| Type  | Value |
| ----- | ----- |
| Time  | O(n²) |
| Space | O(1)  |

---

## ⚠️ Edge Cases

```id="eq11"
- If len(nums) < 3 → return []
- Array with all zeros → only one triplet [0,0,0]
```

---

## 🎯 Pattern Recognition

* Sorting + Two Pointers
* Very common in:

  * 3Sum
  * 4Sum
  * Closest Sum problems

---

## 💡 One-Line Summary

> Fix one element → use two pointers → adjust sum → skip duplicates → store answer

---
