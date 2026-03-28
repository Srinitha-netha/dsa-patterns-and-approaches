# 🚚 Move Zeroes

## 🔗 Problem

https://leetcode.com/problems/move-zeroes/

---

## 🧠 Approach

I used the **two pointer approach** for this problem.

I take two pointers:

* `slow` → keeps track of the position where the next non-zero element should be placed
* `fast` → iterates through the array

While traversing:

* If `nums[fast]` is not equal to 0, I swap it with `nums[slow]`
* Then I increment `slow`

This ensures that all non-zero elements are moved to the front, and zeros automatically shift to the end.

---

## 💡 Idea

We don’t move zeros directly.
Instead:

> Move all non-zero elements forward → zeros will naturally go to the end

---

## ⚡ Complexity

* Time: O(n)
* Space: O(1)

---

## 🔥 Key Point

> Use one pointer to place non-zero elements and another to scan the array

---
