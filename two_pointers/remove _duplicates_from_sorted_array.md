# 🧹 Remove Duplicates from Sorted Array

## 🔗 Problem

https://leetcode.com/problems/remove-duplicates-from-sorted-array/

---

## 🧠 Approach

I used the **two pointer approach** (parallel pointers) for this problem.

Since the array is already sorted, duplicate elements will always be next to each other.

I maintain two pointers:

* `slow` → keeps track of the position of unique elements
* `fast` → traverses the array

I start `slow` from index 0 and move `fast` from index 1.

Whenever `nums[fast]` is not equal to `nums[slow]`,
I increment `slow` and update that position with the new unique value.

This way, all unique elements are placed at the beginning of the array.

---

## 💡 Idea

Because the array is sorted, duplicates are adjacent.
So we only need to compare with the previous unique element.

---

## ⚡ Complexity

* Time: O(n)
* Space: O(1)

---

## 🔥 Key Point

> Use one pointer to track unique elements and another to scan the array

---
