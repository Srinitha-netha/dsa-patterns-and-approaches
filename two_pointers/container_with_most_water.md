# 🪣 Container With Most Water

## 🔗 Problem

https://leetcode.com/problems/container-with-most-water/

---

## 🧠 Approach

I used the **two pointer approach** for this problem.

I initialize two pointers:

* `left = 0`
* `right = n - 1`

At each step, I calculate the current area using:

* width = `right - left`
* height = `min(height[left], height[right])`

So,

```
area = (right - left) * min(height[left], height[right])
```

I keep track of the maximum area by comparing it with the current area.

After that:

* If `height[left] < height[right]`, I move the left pointer forward
* Otherwise, I move the right pointer backward

This continues until both pointers meet.

---

## 💡 Idea

The area depends on the **shorter height**.

So,

> Move the pointer pointing to the smaller height to try getting a better area

---

## ⚡ Complexity

* Time: O(n)
* Space: O(1)

---

## 🔥 Key Point

> Always move the pointer with smaller height, because it limits the area

---
