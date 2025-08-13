
## 📜 Overview
The **Karatsuba algorithm** is a fast multiplication method that reduces the multiplication of two \( n \)-digit numbers to at most **three** multiplications of \( n/2 \)-digit numbers.

This is faster than the traditional O(n²) multiplication algorithm and works in **O(n^{log₂3}) ≈ O(n^{1.585})**.

---

## 🧠 How It Works
Given two numbers `x` and `y`:
1. Split `x` into `a` and `b`.
2. Split `y` into `c` and `d`.
3. Use the formula:
   ```
   x * y = (a * 10^m + b) * (c * 10^m + d)
          = ac * 10^(2m) + ((a+b)*(c+d) - ac - bd) * 10^m + bd
   ```
4. Only **three** multiplications are needed:
   - `ac`
   - `bd`
   - `(a+b)*(c+d)`

---

## 💻 Java Implementation
```java
public class Karatsuba {

    public static long karatsuba(long x, long y) {
        // Base case for recursion
        if (x < 10 || y < 10) {
            return x * y;
        }

        // Calculate size of the numbers
        int size = Math.max(Long.toString(x).length(), Long.toString(y).length());
        int m = size / 2;

        // Split the numbers
        long high1 = x / (long) Math.pow(10, m);
        long low1 = x % (long) Math.pow(10, m);
        long high2 = y / (long) Math.pow(10, m);
        long low2 = y % (long) Math.pow(10, m);

        // Recursive calls
        long z0 = karatsuba(low1, low2);
        long z1 = karatsuba((low1 + high1), (low2 + high2));
        long z2 = karatsuba(high1, high2);

        return (z2 * (long) Math.pow(10, 2 * m)) +
               ((z1 - z2 - z0) * (long) Math.pow(10, m)) +
               z0;
    }

    public static void main(String[] args) {
        long x = 1234;
        long y = 5678;
        System.out.println("Result: " + karatsuba(x, y));
    }
}
```

---

## ⏱️ Time Complexity
- **Traditional multiplication:** O(n²)
- **Karatsuba algorithm:** O(n^{log₂3}) ≈ O(n^{1.585})

---

## 🎯 Key Points
- Works best for **large integers**.
- Uses **divide and conquer**.
- Avoids 1 multiplication step compared to traditional method.

---

## 📚 References
- [Karatsuba Algorithm - Wikipedia](https://en.wikipedia.org/wiki/Karatsuba_algorithm)
