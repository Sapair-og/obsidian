
## 📝 Problem Statement

> Given an integer `n`, compute the number of integers less than or equal to `n` that are **coprime** with `n`.

---

## 📘 Definition

Euler’s Totient Function **φ(n)** counts the number of integers from `1` to `n` that are **coprime** with `n`.

- Two numbers are **coprime** if their `GCD = 1`.

---

## 💡 Formula

If `n` has the prime factorization:

```
n = p₁^e₁ * p₂^e₂ * ... * pk^ek
```

Then:

```
φ(n) = n × (1 - 1/p₁) × (1 - 1/p₂) × ... × (1 - 1/pk)
```

---

## 🔍 Edge Cases

| Case           | φ(n)           |
|----------------|----------------|
| n = 1          | φ(1) = 1       |
| n = prime      | φ(n) = n - 1   |
| n = 0          | Not defined    |
| n = power of p | φ(p^k) = p^k - p^(k-1) |

---

## 🧠 Intuition

- If `n` is a **prime**, then φ(n) = n - 1 (all numbers < n are coprime with n)
- If `n` is **composite**, remove all multiples of its prime factors

---

## 👨‍💻 Java Code (Updated & Clean)

```java
public class TotientFunction {

    public static int phi(int n) {
        if (n == 0) return 0;
        if (n == 1) return 1;

        int result = n;

        for (int p = 2; p * p <= n; ++p) {
            if (n % p == 0) {
                while (n % p == 0) {
                    n /= p;
                }
                result -= result / p;
            }
        }

        // If remaining n is a prime > sqrt(original n)
        if (n > 1) {
            result -= result / n;
        }

        return result;
    }

    public static void main(String[] args) {
        for (int i = 1; i <= 20; i++) {
            System.out.println("φ(" + i + ") = " + phi(i));
        }
    }
}
```

---

## 🧪 Example

```
φ(10) = numbers ≤ 10 that are coprime with 10:
→ {1, 3, 7, 9} → Count = 4

φ(12) = {1, 5, 7, 11} → Count = 4
```

---

## 📦 Time & Space Complexity

- **Time**: O(√n)
- **Space**: O(1)

---

## 🔁 Optional: Sieve Method to Compute φ(1) to φ(N)

```java
public class SieveTotient {
    public static int[] computeTotients(int n) {
        int[] phi = new int[n + 1];

        for (int i = 0; i <= n; i++) {
            phi[i] = i;
        }

        for (int i = 2; i <= n; i++) {
            if (phi[i] == i) { // i is prime
                for (int j = i; j <= n; j += i) {
                    phi[j] -= phi[j] / i;
                }
            }
        }

        return phi;
    }

    public static void main(String[] args) {
        int[] phi = computeTotients(20);
        for (int i = 1; i <= 20; i++) {
            System.out.println("φ(" + i + ") = " + phi[i]);
        }
    }
}
```

---

## ✅ Summary

| Concept              | Details                                       |
|----------------------|-----------------------------------------------|
| Function             | Euler's Totient φ(n)                          |
| Meaning              | Count of numbers ≤ n coprime with n          |
| Prime number         | φ(p) = p - 1                                  |
| Formula              | n × Π(1 - 1/p) for all distinct prime p      |
| Code Variants        | Simple loop, Sieve-based                     |
| Edge Case: φ(1)      | 1                                             |
| Edge Case: φ(0)      | 0 or undefined depending on context          |
