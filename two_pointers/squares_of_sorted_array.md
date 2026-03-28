# 🔢 Squares of a Sorted Array

## 🔗 Problem

https://leetcode.com/problems/squares-of-a-sorted-array/

---

## 🧠 Approach

I used the **two pointer approach** for this problem.

First, I create a new array `res` of the same size as the input array.
Then I initialize:

* `left = 0`
* `right = n - 1`
* `pos = n - 1` (to fill the result from the end)

Since the array can have negative numbers, I compare the **absolute values** of `nums[left]` and `nums[right]`.

* Whichever is greater, I square that value and place it at `res[pos]`
* Then move the corresponding pointer (`left` or `right`)
* Decrease `pos` after every step

I repeat this until all elements are processed.

---

## 💡 Idea

Even though the array is sorted, squaring can disturb the order because of negative numbers.

So instead of sorting again, we:

> Pick the largest square from both ends and fill the result from back to front

---

## ⚡ Complexity

* Time: O(n)
* Space: O(n)

---

## 🔥 Key Point

> Comparing absolute values helps us decide the largest square efficiently without sorting again

---
