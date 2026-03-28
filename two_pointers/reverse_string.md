# 🔄 Reverse String

## 🔗 Problem

https://leetcode.com/problems/reverse-string/

---

## 🧠 Approach

I used the **two pointer approach** here.

I start with one pointer at the beginning (`left`) and one at the end (`right`).
As long as `left < right`, I keep swapping the characters at these positions and move both pointers towards the center.

This way, the string gets reversed in-place without using extra space.

---

## ⚡ Complexity

* Time: O(n)
* Space: O(1)

---

## 💡 Note

The important idea is that we don’t need another array or string —
just swapping is enough to reverse it.

---
