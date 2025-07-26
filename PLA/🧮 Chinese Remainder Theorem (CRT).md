

### 📌 Definition

The **Chinese Remainder Theorem** helps solve systems of **simultaneous congruences** with different moduli (divisors), **when all moduli are pairwise coprime**.

If:

```
x ≡ a₁ mod m₁  
x ≡ a₂ mod m₂  
...  
x ≡ aₙ mod mₙ
```

and **gcd(mi, mj) = 1** for all i ≠ j,  
then there exists a **unique solution modulo (M = m₁ × m₂ × ... × mₙ)**.

---

### 🛠️ Steps to Solve

Given:

```
x ≡ a₁ mod m₁  
x ≡ a₂ mod m₂  
...  
x ≡ aₙ mod mₙ
```

1. **Calculate M** (Product of all moduli):  
    `M = m₁ × m₂ × ... × mₙ`
    
2. For each congruence:
    
    - Let `Mᵢ = M / mᵢ`
        
    - Find inverse `yᵢ` such that:  
        `Mᵢ × yᵢ ≡ 1 mod mᵢ` (Use Extended Euclidean Algorithm)
        
3. Final formula:
    
    ```
    x ≡ (a₁ × M₁ × y₁ + a₂ × M₂ × y₂ + ... + aₙ × Mₙ × yₙ) mod M
    ```
    

---

### 🧠 Tip

- This only works if all moduli are **pairwise coprime** (no common factor except 1).
    
- The result `x` is **unique modulo M**.
    

---

### 🧪 Example

Solve:

```
x ≡ 2 mod 3  
x ≡ 3 mod 4  
x ≡ 2 mod 5
```

1. `M = 3 × 4 × 5 = 60`
    
2. - M₁ = 60 / 3 = 20 → Find y₁: 20 × y₁ ≡ 1 mod 3 → y₁ = 2
        
    - M₂ = 60 / 4 = 15 → Find y₂: 15 × y₂ ≡ 1 mod 4 → y₂ = 3
        
    - M₃ = 60 / 5 = 12 → Find y₃: 12 × y₃ ≡ 1 mod 5 → y₃ = 3
        
3. ```
    x ≡ (2 × 20 × 2 + 3 × 15 × 3 + 2 × 12 × 3) mod 60  
    x ≡ (80 + 135 + 72) mod 60  
    x ≡ 287 mod 60  
    x ≡ 47
    ```

✅ Final Answer: `x ≡ 47 mod 60`

---

### 📚 Applications

- Cryptography (like RSA)
    
- Solving remainder puzzles
    
- Modular arithmetic problems in CP and number theory
    

## 🔢 Solving Linear Congruences with Coefficient of x

### 📘 General Form:

a·x ≡ b mod m  
Where `a`, `b`, and `m` are integers.

Goal: Find the value(s) of `x`.

---

### ✅ Step-by-step Method

1. **Check if solution exists**
    
    - Find `gcd(a, m)`
        
    - If `gcd(a, m)` divides `b`, solution exists.
        
    - Otherwise, ❌ no solution.
        
2. **Simplify the equation** (if gcd ≠ 1)  
    Let `d = gcd(a, m)`  
    Divide everything by `d`:  
    New equation becomes:  
    (a/d)·x ≡ (b/d) mod (m/d)
    
3. **Find modular inverse of the coefficient**  
    You now have:  
    a′·x ≡ b′ mod m′
    
    To isolate `x`, multiply both sides by the modular inverse of a′:
    
    - Find `a_inv` such that:  
        a′·a_inv ≡ 1 mod m′
        
    - Use Extended Euclidean Algorithm to find this inverse.
        
4. **Final answer**  
    x ≡ a_inv · b′ mod m′
    
    If you simplified the equation by dividing by `d`, then you’ll have `d` solutions spaced by (m/d).  
    So the full set of solutions is:  
    x = a_inv · b′ + k·(m/d) where k = 0 to d-1
    

---

## 🧪 Example

Solve: 4x ≡ 8 mod 14

Step 1: Check if solution exists  
gcd(4, 14) = 2, and 2 divides 8 → ✅ so solution exists

Step 2: Simplify the equation  
Divide all terms by 2:  
(4/2)x ≡ (8/2) mod (14/2)  
→ 2x ≡ 4 mod 7

Step 3: Find inverse of 2 mod 7  
We want 2 * x ≡ 1 mod 7  
Try small numbers:  
2 × 1 = 2  
2 × 2 = 4  
2 × 3 = 6  
2 × 4 = 8 ≡ 1 mod 7 ✅  
So, inverse = 4

Step 4: Solve the equation  
x ≡ 4 × 4 = 16 ≡ 2 mod 7

Step 5: Go back to original modulus (14)  
Since we divided by 2 (gcd = 2), we will have 2 solutions spaced by 7:

x = 2, 2 + 7 = 9

✅ Final Answers:  
x ≡ 2 mod 14  
x ≡ 9 mod 14

