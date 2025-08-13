
## 📜 Problem Statement
Given a byte (8 bits), swap its two nibbles.

- **Nibble**: A group of 4 bits.  
- The **left nibble** becomes the right nibble and vice versa.

Example:  
```
Input  : 1001 0110 (0x96)
Output : 0110 1001 (0x69)
```

---

## 💡 Approach
1. Extract the left nibble using bitwise AND (`&`) and shift it right by 4 bits.
2. Extract the right nibble and shift it left by 4 bits.
3. Combine them using bitwise OR (`|`).

---

## 📦 Java Code

```java
public class SwapNibbles {
    public static int swapNibbles(int num) {
        // Extract right nibble and shift it to left
        int leftShift = (num & 0x0F) << 4;
        // Extract left nibble and shift it to right
        int rightShift = (num & 0xF0) >> 4;
        // Combine both
        return (leftShift | rightShift);
    }

    public static void main(String[] args) {
        int num = 0x96; // Example byte
        int result = swapNibbles(num);
        System.out.printf("Original: 0x%02X, After Swap: 0x%02X%n", num, result);
    }
}
```

---

## 🧮 Example Walkthrough
For `0x96` (binary `1001 0110`):

1. **Right nibble** = `0110` → shift left → `0110 0000`
2. **Left nibble**  = `1001` → shift right → `0000 1001`
3. Combine → `0110 1001` (0x69)

✅ Done!

---

## 🏁 Complexity
- **Time Complexity**: O(1) (just bitwise operations)
- **Space Complexity**: O(1)

---

## 📌 Notes
- Works for integers but only affects the **lowest byte**.
- Bitwise operations are faster than string/array manipulation.
