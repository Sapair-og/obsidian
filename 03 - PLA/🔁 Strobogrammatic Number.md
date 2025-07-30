

### 📌 Definition

A **strobogrammatic number** is a number that looks the **same when rotated 180 degrees** (i.e., flipped upside down).

---

## 🔍 Examples

|Number|Upside-down|Valid?|
|---|---|---|
|`69`|`96`|✅ Yes|
|`88`|`88`|✅ Yes|
|`818`|`818`|✅ Yes|
|`962`|`296`|❌ No|

---

## ✅ Valid Strobogrammatic Digit Pairs

|Normal|Rotated|
|---|---|
|`0`|`0`|
|`1`|`1`|
|`6`|`9`|
|`8`|`8`|
|`9`|`6`|

---

## ❌ Invalid Digits

These digits break the rule:

- `2`, `3`, `4`, `5`, `7`
    

---

## 🧠 Idea

- Use **two pointers**: one at start, one at end.
    
- Match each digit pair with its valid strobogrammatic partner.
    
- If any mismatch → not a strobogrammatic number.
    

---

## 🧪 Java Code

```java
public class StrobogrammaticNumber {

    public static boolean isStrobogrammatic(String num) {
        int left = 0;
        int right = num.length() - 1;

        while (left <= right) {
            char l = num.charAt(left);
            char r = num.charAt(right);

            if (!isValidPair(l, r)) {
                return false;
            }

            left++;
            right--;
        }
        return true;
    }

    private static boolean isValidPair(char l, char r) {
        if (l == '0' && r == '0') return true;
        if (l == '1' && r == '1') return true;
        if (l == '6' && r == '9') return true;
        if (l == '9' && r == '6') return true;
        if (l == '8' && r == '8') return true;
        return false;
    }

    public static void main(String[] args) {
        System.out.println(isStrobogrammatic("69"));   // true
        System.out.println(isStrobogrammatic("88"));   // true
        System.out.println(isStrobogrammatic("962"));  // false
    }
}
```

---

## ⏱ Time & Space Complexity

|Operation|Complexity|
|---|---|
|Time|O(n)|
|Space|O(1)|

---

## 📚 Use-Cases

- Pattern matching problems
    
- Number transformation questions
    
- Rotation-based puzzles
    
