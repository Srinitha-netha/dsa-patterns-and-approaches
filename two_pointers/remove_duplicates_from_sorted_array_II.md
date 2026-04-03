# 🔶 Remove Duplicates from Sorted Array II – Optimal Approach (Two Pointers)

---

## 🔗 Problem Link

* LeetCode: https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/

---

## 📌 Problem

Given a sorted array `nums`, remove duplicates **in-place** such that each element appears **at most twice**.

Return the **new length** after removing extra duplicates.

---

## 🚀 Intuition

* This is an extension of **Remove Duplicates I**
* Instead of allowing only one occurrence, we allow **at most two**
* So we must **skip elements appearing more than twice**

👉 Key Idea:
Compare the current element with the element **2 positions before**

---

## 🧠 Core Idea

```text id="c6r9tp"
Allow element only if:
nums[fast] != nums[slow - 2]
```

---

## ⚙️ Algorithm (Two Pointers)

```text id="a9x3vu"
1. If length <= 2:
      return length

2. Initialize:
      slow = 2

3. Traverse fast from 2 → n-1:

      If nums[fast] != nums[slow - 2]:
            nums[slow] = nums[fast]
            slow++

4. Return slow
```

---

## 🧪 Dry Run (ASCII)

```text id="z4k1mj"
nums = [1,1,1,2,2,3]

slow = 2

Check:
nums[fast]=1, nums[slow-2]=1 → skip

nums[fast]=2 → valid → place at slow

Final array:
[1,1,2,2,3]
```

---

## ⚡ Key Insights

* Compare with `slow - 2` (not just previous element)
* Ensures maximum **2 duplicates allowed**
* In-place modification → no extra space

---

## ⏱️ Complexity

| Type  | Value |
| ----- | ----- |
| Time  | O(n)  |
| Space | O(1)  |

---

## ⚠️ Edge Cases

```text id="k2v8rb"
- nums length <= 2 → return as is
- All elements same → keep only 2
- No duplicates → return full array
```

---

## 🎯 Pattern Recognition

* Two Pointers
* In-place Array Modification
* Generalization of duplicate removal

---

## 💡 One-Line Summary

> Use two pointers and allow an element only if it differs from nums[slow - 2]

---
