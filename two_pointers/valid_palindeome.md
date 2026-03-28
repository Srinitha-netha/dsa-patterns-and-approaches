# 🔍 Valid Palindrome

## 🔗 Problem

https://leetcode.com/problems/valid-palindrome/

---

## 🧠 Approach

This problem can be efficiently solved using the **Two Pointer technique**.

We initialize two pointers:

* `left` at the beginning
* `right` at the end

Instead of preprocessing the string, we handle everything in a single pass:

* Skip non-alphanumeric characters using `isalnum()`
* Compare characters in a **case-insensitive** way
* If mismatch occurs → return `False`
* Otherwise, move both pointers inward

This continues until both pointers meet.

---

## 💡 Idea

Think of it like checking a **mirror**:

* Start from both ends
* Ignore unnecessary characters
* Compare only meaningful ones

If all pairs match → it's a palindrome ✅

---

## ⚡ Complexity

* **Time Complexity:** O(n)
* **Space Complexity:** O(1)

---

## 🔑 Key Insight

Instead of creating a new filtered string, we:

> Skip unwanted characters *during traversal*

This keeps the solution both **efficient** and **clean**.

---

## 🚀 Takeaway

* Two pointers are powerful for **symmetry problems**
* Always try to **optimize space** by avoiding extra structures
* Handle edge cases inline rather than separately

---
