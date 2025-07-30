

### 🛠️ Key Approach

- Avoid converting the full array to an integer (to prevent overflow on large inputs).
    
- Use **digit-by-digit addition from the least significant digit** (end of array).
    
- Simulate **manual addition** like how we do on paper.


---

### 🧾 Algorithm Steps

1. Start from the last index of the array.
    
2. Add the current digit with `K % 10` and any carry.
    
3. Update `K` using integer division (`K /= 10`).
    
4. Handle carry if the sum > 9.
    
5. Insert the result at the beginning (or use a LinkedList).
    
6. Repeat until both array and `K` are fully processed.
    

---

### 🔄 Optimizations

- **Reversing the array** helps in appending digits efficiently (O(1)).
    
- **Modulo and division** help isolate digits from `K`.
    
- **Carry handling** ensures accuracy across digit positions.
    

---

### ⏱️ Time Complexity

- `O(n)` where `n = max(num.length, digits in K)`
    
- Efficient and scalable for large inputs.
    

---

### 💡 Key Insights

- Simulates real-world addition without large number conversions.
    
- Works for very large `num` arrays or values of `K`.
    
- Avoids using `int` or `long`, which can overflow.
    
- Practical and commonly asked in coding interviews.  
-

