# 🔹 Two Pointers Pattern

## 🧠 What is Two Pointers?

The Two Pointers technique is a method where we use **two indices (pointers)** to traverse a data structure (usually an array or string) instead of using nested loops.

This helps in reducing time complexity, often from **O(n²) → O(n)**.

---

## 🎯 When to Use

Use Two Pointers when:

* The array is **sorted**
* You need to find **pairs or triplets**
* You are working with **both ends of the array**
* You want to **optimize brute force solutions**

---

## 🪜 General Approach

1. Initialize two pointers:

   * `left = 0`
   * `right = n - 1`

2. Traverse while `left < right`

3. Based on condition:

   * Move `left` pointer forward (`left++`)
   * Move `right` pointer backward (`right--`)

4. Continue until condition is satisfied

---

## 🔄 Types of Two Pointers

### 1. Opposite Direction

* One pointer at start, one at end
* Move inward
* Example use: pair sum problems

---

### 2. Same Direction (Fast & Slow)

* Both pointers move forward
* One moves faster than the other
* Example use: cycle detection, removing duplicates

---

## 🔥 Key Insight

Instead of checking all possible combinations,
we **eliminate unnecessary cases using pointer movement**.

---

## ⚡ Complexity

* Time: Usually **O(n)**
* Space: **O(1)**

---

## ❌ Common Mistakes

* Not understanding **when to move which pointer**
* Using Two Pointers on **unsorted arrays incorrectly**
* Forgetting edge cases (duplicates, boundaries)

---

## 💡 One-Line Summary

Use two pointers to efficiently traverse and reduce unnecessary comparisons.
