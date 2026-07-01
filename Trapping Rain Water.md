# 🌧️ Trapping Rain Water

## 🔗 Problem

https://leetcode.com/problems/trapping-rain-water/

---

## 🧠 Approach

I used a **precomputation approach** to solve this problem.

For each index, the water trapped depends on:

* Maximum height to the left
* Maximum height to the right

So I first compute:

* `maxLeft[i]` → maximum height from left to index `i`
* `maxRight[i]` → maximum height from right to index `i`

Then, for each index:

> water at i = min(maxLeft[i], maxRight[i]) - height[i]

If the result is negative, I treat it as 0.

Finally, I sum up the water at all positions.

---

## ⚙️ Code

```python id="trapcode01"
class Solution:
    def trap(self, height: List[int]) -> int:
        n = len(height)

        maxLeft = [0] * n
        maxRight = [0] * n

        maxLeft[0] = height[0]
        for i in range(1, n):
            maxLeft[i] = max(maxLeft[i - 1], height[i])

        maxRight[n - 1] = height[n - 1]
        for i in range(n - 2, -1, -1):
            maxRight[i] = max(maxRight[i + 1], height[i])

        trapWater = 0

        for i in range(n):
            currWater = min(maxLeft[i], maxRight[i]) - height[i]
            if currWater < 0:
                currWater = 0
            trapWater += currWater

        return trapWater
```

---

## ⚡ Complexity

* Time: O(n)
* Space: O(n)

---

## 💡 Key Idea

At each index, water trapped depends on the **minimum of left and right maximum boundaries**.

---

## 🔥 Insight

> Precompute boundaries first, then calculate contribution at each index.

---
