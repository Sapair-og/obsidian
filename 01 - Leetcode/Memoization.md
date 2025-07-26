

### 📌 Problem: [1137. N-th Tribonacci Number (LeetCode)](https://leetcode.com/problems/n-th-tribonacci-number/)

> The Tribonacci sequence is defined as:
> 
> ```
> T(0) = 0  
> T(1) = 1  
> T(2) = 1  
> T(n) = T(n-1) + T(n-2) + T(n-3), for n ≥ 3
> ```
> 
> Return the value of T(n).

---

### 🚫 Naive Recursion (TLE)

```java
public int tribonacci(int n) {
    if (n == 0) return 0;
    if (n == 1 || n == 2) return 1;
    return tribonacci(n - 1) + tribonacci(n - 2) + tribonacci(n - 3);
}
```

- ❌ Time Complexity: **O(3^n)** — recalculates the same values over and over.
    
- ❌ Causes **Time Limit Exceeded** for large `n`.
    

---

### ✅ Solution: Memoization (Top-Down DP)

> Memoization = store already-calculated results and reuse them.

#### Java Code (Using HashMap):

```java
import java.util.HashMap;

class Solution {
    HashMap<Integer, Integer> memo = new HashMap<>();

    public int tribonacci(int n) {
        if (n == 0) return 0;
        if (n == 1 || n == 2) return 1;

        if (memo.containsKey(n)) return memo.get(n);

        int result = tribonacci(n - 1) + tribonacci(n - 2) + tribonacci(n - 3);
        memo.put(n, result);
        return result;
    }
}
```

#### ✅ Time & Space:

- Time: **O(n)**
    
- Space: **O(n)** (for memoization)
    

---

### 🔁 Alternative: Bottom-Up DP (Tabulation)

> More efficient for this case, avoids recursion stack.

```java
class Solution {
    public int tribonacci(int n) {
        if (n == 0) return 0;
        if (n == 1 || n == 2) return 1;

        int a = 0, b = 1, c = 1;
        for (int i = 3; i <= n; i++) {
            int next = a + b + c;
            a = b;
            b = c;
            c = next;
        }
        return c;
    }
}
```

#### ✅ Time & Space:

- Time: **O(n)**
    
- Space: **O(1)** (constant space)
    

---

## 🧠 What is Memoization?

- Memoization is an optimization for recursive functions.
    
- It **caches** results of expensive function calls and **returns the cached result** when the same inputs occur again.
    
- Used in problems with **overlapping subproblems** (like Fibonacci, Tribonacci, Climbing Stairs, etc.)
    

#### Example Logic:

```java
if (memo.containsKey(n)) return memo.get(n);
else {
    int result = trib(n-1) + trib(n-2) + trib(n-3);
    memo.put(n, result);
}
```

---

## 📚 Summary

|Approach|Time|Space|Notes|
|---|---|---|---|
|Naive Recursion|O(3^n)|O(n)|❌ Too slow, avoid it|
|Memoization|✅O(n)|✅O(n)|Fast and easy to implement|
|Bottom-Up DP|✅O(n)|✅O(1)|Best performance (constant space)|

keep backup
