
### 📌 Goal

Check if a number's **binary representation** is a **palindrome** (same forwards and backwards).

---

## ✅ What is a Binary Palindrome?

A number is a binary palindrome if its binary form looks the same when reversed.

### 🔁 Examples

- `5` → Binary: `101` → ✅ Palindrome
    
- `9` → Binary: `1001` → ✅ Palindrome
    
- `10` → Binary: `1010` → ❌ Not a palindrome
    

---

## 📘 Step-by-Step (String Method)

1. Convert the number to binary string.
    
2. Reverse the string.
    
3. Compare both → if same → it's a palindrome.
    

---

## 🧪 Java Code (Using Strings)

```java
public class BinaryPalindrome {

    public static boolean isBinaryPalindrome(int n) {
        String binary = Integer.toBinaryString(n);         // Convert to binary
        String reversed = new StringBuilder(binary).reverse().toString();  // Reverse it
        return binary.equals(reversed);                    // Compare both
    }

    public static void main(String[] args) {
        System.out.println(isBinaryPalindrome(5));   // true
        System.out.println(isBinaryPalindrome(10));  // false
    }
}
```

---

## 💡 Bitwise Approach (No Strings)

This method checks bits from both ends without converting to string.

```java
public class BinaryPalindromeBitwise {

    public static boolean isBinaryPalindrome(int n) {
        int left = Integer.SIZE - Integer.numberOfLeadingZeros(n) - 1;
        int right = 0;

        while (left > right) {
            if (((n >> left) & 1) != ((n >> right) & 1)) {
                return false;
            }
            left--;
            right++;
        }
        return true;
    }

    public static void main(String[] args) {
        System.out.println(isBinaryPalindrome(5));   // true
        System.out.println(isBinaryPalindrome(10));  // false
    }
}
```

---

## ⏱ Time & Space Complexity

|Method|Time Complexity|Space Complexity|
|---|---|---|
|String|O(k)|O(k)|
|Bitwise|O(k)|O(1)|

> Where `k` = number of bits in the number

---

## 📌 When to Use:

- In coding interviews
    
- While learning bitwise operations
    
- When solving binary number pattern problems
    
