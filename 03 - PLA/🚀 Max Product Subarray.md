
### 📝 Problem Statement

> Given an integer array `nums`, find the **contiguous subarray** (containing at least one number) which has the **largest product**, and return that product.

---

### 🧠 Intuition

This is like the **maximum subarray sum** problem (Kadane’s algorithm), but with **products**.

But there's a twist:

- **Negative × Negative = Positive** → might help!
    
- **Zero** resets the product.
    

So, we **track both**:

- `maxSoFar`: current maximum product
    
- `minSoFar`: current minimum product (used when negatives flip signs)
    

---

### 👨‍💻 Java Code

```java
public class MaxProductSubarray {
    public static int maxProduct(int[] nums) {
        int maxProd = nums[0];
        int minProd = nums[0];
        int result = nums[0];

        for (int i = 1; i < nums.length; i++) {
            int curr = nums[i];

            if (curr < 0) {
                // Swap max and min when negative appears
                int temp = maxProd;
                maxProd = minProd;
                minProd = temp;
            }

            // Either take the current element, or extend previous product
            maxProd = Math.max(curr, curr * maxProd);
            minProd = Math.min(curr, curr * minProd);

            // Update result
            result = Math.max(result, maxProd);
        }

        return result;
    }

    public static void main(String[] args) {
        int[] nums = {2, 3, -2, 4};
        System.out.println("Max Product Subarray: " + maxProduct(nums)); // Output: 6
    }
}
```

---

### 🔍 Example

```
Input: [2,3,-2,4]
→ Subarray [2,3] → Product = 6 (Max)

Input: [-2,0,-1]
→ Subarray [-1] → Product = 0
```

---

### 🧠 Key Observations

- Multiplying by a **negative number** flips min ↔ max
    
- Multiplying by **0** resets product
    
- You **must** track both `max` and `min` at each step
    

---

### 📦 Time & Space Complexity

- **Time**: `O(n)` → one pass
    
- **Space**: `O(1)` → constant space used
    

---

### ✅ Summary

|Concept|Notes|
|---|---|
|Negative values|Can turn small product into large one|
|Zero|Resets current product|
|Track min & max|Because of sign flipping|
|Swap on negative|Handle with temp variable|
