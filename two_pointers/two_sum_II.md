# Two Sum II - Input Array Is Sorted

🔗 Problem Link: https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/

---

## 🧩 Problem

Find two numbers such that they add up to a specific target number.
The input array is sorted in non-decreasing order, and the output should be 1-based indices.

---

## 🐢 Brute Force

* Use two nested loops to check all possible pairs
* If a pair sums to target, return their indices

**Time Complexity:** O(n²)
**Space Complexity:** O(1)

---

## ⚡ Optimized Approach (Two Pointers)

### 🧠 Idea

Since the array is sorted, we can use two pointers to efficiently find the pair.

---

### 🪜 Steps

1. Initialize two pointers:

   * `left = 0`
   * `right = n - 1`

2. Traverse while `left < right`:

   * Compute sum = arr[left] + arr[right]

3. If sum == target:

   * Return `(left + 1, right + 1)` (1-based indexing)

4. If sum < target:

   * Move `left` forward to increase sum

5. If sum > target:

   * Move `right` backward to decrease sum

---

## 🔥 Key Insight

Because the array is sorted:

* Moving the left pointer increases the sum
* Moving the right pointer decreases the sum

This eliminates unnecessary comparisons and reduces time complexity.

---

## ⏱ Complexity

* **Time:** O(n)
* **Space:** O(1)

---

## 💡 One-Line Summary

U
