
### 📌 Purpose:

Efficiently find **all prime numbers** in a range from `L` to `R` using a boolean array.

---

### ✅ Algorithm Steps:

1. Create a boolean array `isPrime[]` of size `R + 1`, initialized to `true`.
    
2. Mark `isPrime[0]` and `isPrime[1]` as `false` (0 and 1 are not prime).
    
3. Loop from `2` to `√R`:
    
    - If `isPrime[i]` is `true`, mark all its multiples as `false`.
        
        - Start from `i * i` and go up to `R` in steps of `i`.
            
4. Loop from `L` to `R` and print numbers where `isPrime[i]` is `true`.
    

---

### 🧠 Time Complexity:

- **Preprocessing:** `O(n log log n)`
    
- **Space Complexity:** `O(n)`
    

---

### 💻 Java Code Example:

```java
public class SievePrimeRange {
    public static void main(String[] args) {
        int L = 10;
        int R = 50;

        boolean[] isPrime = new boolean[R + 1];

        // Step 1: Assume all numbers are prime
        for (int i = 2; i <= R; i++) {
            isPrime[i] = true;
        }

        // Step 2: Sieve of Eratosthenes
        for (int i = 2; i * i <= R; i++) {
            if (isPrime[i]) {
                for (int j = i * i; j <= R; j += i) {
                    isPrime[j] = false;
                }
            }
        }

        // Step 3: Print primes in range L to R
        System.out.println("Prime numbers between " + L + " and " + R + ":");
        for (int i = L; i <= R; i++) {
            if (isPrime[i]) {
                System.out.print(i + " ");
            }
        }
    }
}
```

---

### 📌 Example Output:

```
Prime numbers between 10 and 50:
11 13 17 19 23 29 31 37 41 43 47
```

---
