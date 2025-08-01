

## 📌 Problem Definition  
In an array, an element is called a **leader** if it is **greater than or equal to all elements to its right**.

---

## 🧠 Example

Given:
```
[16, 17, 4, 3, 5, 2]
```

✅ Leaders are: `17`, `5`, `2`

- `2` is last → always a leader  
- `5 > 2` → leader  
- `3 < 5` → not a leader  
- `4 < 5` → not a leader  
- `17 > all to its right` → leader  
- `16 < 17` → not a leader
s
---

## 🧪 Brute Force Approach

- For each element, check all elements to its right.
- Time Complexity: **O(n²)**  
❌ Not efficient for large arrays.

---

## ⚡ Optimized Approach (Right to Left)

### 💡 Idea:
- Start from the **rightmost** element (it's always a leader).
- Track the **maximum so far**.
- If current element ≥ max so far → it's a leader.

---

## ✅ Java Code

```java
import java.util.*;

public class ArrayLeaders {

    public static List<Integer> findLeaders(int[] arr) {
        List<Integer> leaders = new ArrayList<>();
        int n = arr.length;

        int maxFromRight = arr[n - 1];
        leaders.add(maxFromRight);  // Last element is always a leader

        // Traverse from second last to first
        for (int i = n - 2; i >= 0; i--) {
            if (arr[i] >= maxFromRight) {
                maxFromRight = arr[i];
                leaders.add(maxFromRight);
            }
        }

        // Since we added from right to left, reverse the result
        Collections.reverse(leaders);
        return leaders;
    }

    public static void main(String[] args) {
        int[] arr = {16, 17, 4, 3, 5, 2};
        System.out.println("Leaders: " + findLeaders(arr));
    }
}
```

---

## 🧾 Output:
```
Leaders: [17, 5, 2]
```

---

## ⏱ Time and Space Complexity

| Metric        | Value     |
|---------------|-----------|
| Time          | O(n)      |
| Space (output)| O(k)      |

> Where `k` is number of leaders

---

## ✅ Use Cases

- Common interview problem
- Useful in:
  - Stock price analysis
  - Maximum from right-side problems
  - Competitive coding

---
