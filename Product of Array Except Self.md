# ➗ Product of Array Except Self

## 🔗 Problem

https://leetcode.com/problems/product-of-array-except-self/

---

## 🧠 Approach

I used the **prefix and suffix product approach with extra space**.

First, I create two additional arrays:

* `left[i]` → stores product of all elements to the left of index `i`
* `right[i]` → stores product of all elements to the right of index `i`

Then, for each index:

> result[i] = left[i] × right[i]

This makes it easy to compute the final output in O(n) time.

---

## ⚙️ Code Snippet

```python id="5xq9kd"
def productExceptSelf(nums):
    n = len(nums)

    left = [1] * n
    right = [1] * n
    res = [1] * n

    # build left product array
    for i in range(1, n):
        left[i] = left[i - 1] * nums[i - 1]

    # build right product array
    for i in range(n - 2, -1, -1):
        right[i] = right[i + 1] * nums[i + 1]

    # final result
    for i in range(n):
        res[i] = left[i] * right[i]

    return res
```

---

## ⚡ Complexity

* Time: O(n)
* Space: O(n)

---

## 🔥 Key Insight

> Precomputing left and right products makes it easy to calculate the final result in one pass

---

## 🚀 Takeaway

* Extra arrays make logic simpler and easier to understand
* Prefix and suffix patterns are very powerful for array problems
* Optimization can come later once the idea is clear

---
