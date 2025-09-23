# Boolean Algebra (a.k.a. Logic Gym)

Boolean algebra is how we reason about 0s and 1s. It’s also your best friend for turning messy logic into elegant circuits.

---

## Basics

- **AND (·)**: 1 if both are 1
- **OR (+)**: 1 if at least one is 1
- **NOT (‾)**: flips 0 ↔ 1

Truth snippet:
```
A B | A·B A+B ¬A
0 0 |  0   0  1
0 1 |  0   1  1
1 0 |  0   1  0
1 1 |  1   1  0
```

### Exercise
- Write the truth table for XOR using only A, B, and Boolean ops.

---

## Intermediate

### Greatest Hits (Laws)
- Identity: A+0=A, A·1=A
- Null: A+1=1, A·0=0
- Idempotent: A+A=A, A·A=A
- Complement: A+¬A=1, A·¬A=0
- Commutative/Associative/Distributive
- De Morgan: ¬(A·B)=¬A+¬B, ¬(A+B)=¬A·¬B

### Simplification Example
Simplify: F=A·B + A·¬B → F = A·(B+¬B) = A

### Karnaugh Maps (K‑maps)
- Visual method to group 1s and reduce expressions (2–4 variables comfortably)

### Exercise
- Minimize F(A,B,C)=Σm(1,3,5,7) using a K‑map.

---

## Advanced

### SOP/POS Forms
- Sum‑of‑Products vs Product‑of‑Sums trade‑offs for implementation

### Don’t Cares (X)
- Treat unused input combos as flexible to further simplify logic

### Multi‑Level Logic and Factoring
- Reduce gate count and depth by factoring expressions

### Exercise
- Given F = A·B + A·C + B·C, factor to reduce gate count and sketch a low‑depth implementation.
