

### 📝 Problem Statement

> Given an array `nums`, find the **majority element** that appears **more than ⌊n/2⌋ times**.  
> Assume majority element **always exists**.

---

## 1️⃣ Brute Force (Count using n/2)

### 💡 Idea

Count frequency of each element manually and check if it’s more than `n/2`.

---

### 👨‍💻 Code (Java)

```java
public class MajorityElementBrute {
    public static int findMajorityElement(int[] nums) {
        int n = nums.length;
        
        for (int i = 0; i < n; i++) {
            int count = 0;
            
            for (int j = 0; j < n; j++) {
                if (nums[i] == nums[j]) {
                    count++;
                }
            }

            if (count > n / 2) {
                return nums[i];
            }
        }

        return -1; // won't be reached since majority always exists
    }

    public static void main(String[] args) {
        int[] nums = {3, 3, 4, 2, 3};
        System.out.println("Majority Element: " + findMajorityElement(nums));
    }
}
```

---

### ⏱️ Time & Space Complexity

- **Time**: O(n²) ❌ (slow for big inputs)
    
- **Space**: O(1)
    

---

## 2️⃣ HashMap Frequency Count

### 💡 Idea

Use a HashMap to count how many times each number appears.

---

### 👨‍💻 Code (Java)

```java
import java.util.HashMap;

public class MajorityElementMap {
    public static int findMajorityElement(int[] nums) {
        HashMap<Integer, Integer> map = new HashMap<>();
        int n = nums.length;

        for (int num : nums) {
            map.put(num, map.getOrDefault(num, 0) + 1);

            if (map.get(num) > n / 2) {
                return num;
            }
        }

        return -1; // won't be reached
    }

    public static void main(String[] args) {
        int[] nums = {2, 2, 1, 1, 1, 2, 2};
        System.out.println("Majority Element: " + findMajorityElement(nums));
    }
}
```

---

### ⏱️ Time & Space Complexity

- **Time**: O(n)
    
- **Space**: O(n) (for HashMap)
    

---

## ✅ Summary

|Method|Time|Space|Best For|
|---|---|---|---|
|Brute Force (n²)|O(n²)|O(1)|Learning / Small Inputs|
|HashMap Count|O(n)|O(n)|Simple and Fast|
|Moore’s Algorithm|O(n)|O(1)|Best Optimized Performance|
