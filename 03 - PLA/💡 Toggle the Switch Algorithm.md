
## 📝 Problem Statement (General Form)

> You are given a set of **switches** or **bulbs** (usually represented as an array or bits).  
Toggling means switching a state from `ON → OFF` or `OFF → ON`.  

For example:
- `1 → 0`
- `0 → 1`

Your task might be:
- Toggle a switch at index `i`
- Toggle a switch and its neighbors
- Perform multiple toggles with given conditions

---

## 🔄 Basic Toggle Logic

### 🧠 Using XOR

To toggle a binary switch:
```java
value = value ^ 1;
```

Explanation:
- `0 ^ 1 = 1`
- `1 ^ 1 = 0`

So XOR with 1 flips the bit!

---

## 🔧 Java Example 1: Toggle Each Switch

```java
public class ToggleSwitches {
    public static void main(String[] args) {
        int[] switches = {1, 0, 1, 1, 0}; // Initial state

        for (int i = 0; i < switches.length; i++) {
            switches[i] = switches[i] ^ 1; // Toggle
        }

        for (int sw : switches) {
            System.out.print(sw + " ");  // Output: 0 1 0 0 1
        }
    }
}
```

---

## 🔧 Java Example 2: Toggle ith Switch and Neighbors

```java
public class ToggleNeighbors {
    public static void toggle(int[] arr, int i) {
        int n = arr.length;

        // Toggle current
        arr[i] ^= 1;

        // Toggle left neighbor
        if (i - 1 >= 0) arr[i - 1] ^= 1;

        // Toggle right neighbor
        if (i + 1 < n) arr[i + 1] ^= 1;
    }

    public static void main(String[] args) {
        int[] switches = {1, 0, 1, 1, 0};

        toggle(switches, 2);  // Toggle switch at index 2 and its neighbors

        for (int sw : switches) {
            System.out.print(sw + " ");  // Output: 1 1 0 0 0
        }
    }
}
```

---

## ⚡ Real-World Analogy

Think of a row of light bulbs:
- Touching one bulb might toggle itself **and** nearby bulbs.
- You need to apply the correct toggles to reach a **desired pattern** (all OFF, all ON, etc.)

---

## 📦 Time & Space Complexity

- **Time**: Depends on toggling logic, usually `O(n)` or `O(1)` per operation.
- **Space**: `O(1)` extra if done in-place.

---

## 🧠 Tip

You can also use:
```java
value = (value == 1) ? 0 : 1;
```
But `value ^= 1` is faster and cleaner.

---

## ✅ Summary

| Concept        | Description                          |
|----------------|--------------------------------------|
| Toggle         | Flip 0 ↔ 1                           |
| XOR with 1     | Efficient way to toggle              |
| With neighbors | Carefully check bounds (i-1, i+1)    |
| Used in        | Bit manipulation, switch puzzles     |
