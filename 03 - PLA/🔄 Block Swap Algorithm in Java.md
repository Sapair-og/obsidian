
## 📜 Overview
The **Block Swap Algorithm** is used to **rotate an array** by `d` positions to the left (or right).  
It works by dividing the array into blocks and swapping them recursively until the rotation is complete.  
This algorithm runs in **O(n)** time and uses **O(1)** extra space.

---

## 🛠 Algorithm Steps
1. Let `arr[]` be the input array of size `n`.
2. Rotation by `d` means:
   - Move the first `d` elements to the end **in the same order**.
3. Instead of moving elements one by one:
   - Divide the array into two parts:
     - **A** → First `d` elements.
     - **B** → Remaining `n - d` elements.
   - Swap the smaller block with an equal portion of the other block.
   - Recurse on the remaining unrotated portion until fully rotated.

---

## 🖼 Visual Example
Before rotation (`d = 2`):

```
[ 1  2 | 3  4  5  6  7 ]
   A       B
```

Swap step:

```
[ 3  4 | 1  2 | 5  6  7 ]
   B'     A
```

After recursion:

```
[ 3  4  5  6  7  1  2 ]
```

---

## 💻 Java Implementation

```java
public class BlockSwapRotation {

    // Function to swap array elements
    private static void swap(int[] arr, int fi, int si, int d) {
        for (int i = 0; i < d; i++) {
            int temp = arr[fi + i];
            arr[fi + i] = arr[si + i];
            arr[si + i] = temp;
        }
    }

    // Recursive block swap method
    private static void leftRotateRec(int[] arr, int i, int d, int n) {
        if (d == 0 || d == n) return;
        if (d == n - d) {
            swap(arr, i, n - d + i, d);
            return;
        }

        if (d < n - d) {
            swap(arr, i, n - d + i, d);
            leftRotateRec(arr, i, d, n - d);
        } else {
            swap(arr, i, d + i, n - d);
            leftRotateRec(arr, n - d + i, 2 * d - n, d);
        }
    }

    // Main function to rotate array
    public static void leftRotate(int[] arr, int d) {
        int n = arr.length;
        if (d == 0 || d == n) return;
        leftRotateRec(arr, 0, d, n);
    }

    // Utility to print array
    private static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6, 7};
        int d = 2;

        System.out.println("Original Array:");
        printArray(arr);

        leftRotate(arr, d);

        System.out.println("Array after left rotation by " + d + " positions:");
        printArray(arr);
    }
}
```

---

## ⏱ Complexity
- **Time Complexity**: `O(n)` — each element is swapped once.
- **Space Complexity**: `O(1)` — no extra array used.

---

## 📌 Example
**Input:**
```
arr = [1, 2, 3, 4, 5, 6, 7], d = 2
```
**Output:**
```
[3, 4, 5, 6, 7, 1, 2]
```

---

## 🧠 Key Points
- Works **in-place** with no extra storage.
- Faster than naive rotation for large arrays.
- Handles both small and large rotations efficiently.
