# 🔄 Rotate Image (90° Clockwise)

## 🔗 Problem

https://leetcode.com/problems/rotate-image/

---

## 🧠 Approach

I used a **two-step in-place approach**:

### Step 1: Transpose the matrix

Swap elements across the diagonal:

> matrix[i][j] ↔ matrix[j][i]

This converts rows into columns.

### Step 2: Reverse each row

After transposing, reverse every row to get the final rotated matrix.

---

## ⚙️ Code

```python id="rot01"
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        n = len(matrix)

        # Step 1: Transpose
        for i in range(n):
            for j in range(i + 1, n):
                matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]

        # Step 2: Reverse each row
        for i in range(n):
            for j in range(n // 2):
                matrix[i][j], matrix[i][n - j - 1] = matrix[i][n - j - 1], matrix[i][j]
```

---

## ⚡ Complexity

* Time: O(n²)
* Space: O(1)

---

## 💡 Key Idea

> Transpose flips rows into columns, reversing each row completes the 90° rotation.

---

## 🔥 Insight

Instead of creating a new matrix, we modify it **in-place using transpose + reverse**.

---
