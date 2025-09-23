# Logic Gates

Tiny boxes, big impact. Each gate computes a simple Boolean function. Together, they build adders, ALUs, and beyond.

---

## Basics

- **NOT**: flips a bit
- **AND / OR**: combine inputs by “both” or “either”
- **NAND / NOR**: AND/OR with a NOT on the output (surprisingly universal!)
- **XOR / XNOR**: “different?” vs “same?”

### Truth Tables
```
A B | AND OR NAND NOR XOR XNOR
0 0 |  0   0   1    1   0   1
0 1 |  0   1   1    0   1   0
1 0 |  0   1   1    0   1   0
1 1 |  1   1   0    0   0   1
```

### Exercise
- Implement XOR using only AND, OR, NOT.

---

## Intermediate

### Universality
- **NAND** alone can implement any logic. Same for **NOR**.
- If you can express it in AND/OR/NOT, you can realize it with NAND gates.

### From Gates to Modules
- Half adder = XOR (sum) + AND (carry)
- Full adder = 2× half adder + OR
- Ripple-carry adder = chain full adders; delay grows with bit‑width

### Exercise
- Sketch a 1‑bit full adder using two half adders and an OR.

---

## Advanced

### Gate‑Level Realities
- Fan‑out: too many loads slow edges
- Glitches/hazards: different path delays cause temporary spikes
- Critical path: longest logic delay limits your clock speed

### Mitigations
- Balance logic depth, buffer high fan‑out nets
- Use synchronous design: register boundaries “reset” timing

### Exercise
- Identify a potential static hazard in `F = A·B + A·¬B + ¬A·C` and suggest a fix.

---

## Implementation Notes

- Prefer minimal logic depth for speed; factor expressions
- Use XOR wisely—expensive in some libraries vs sum-of-products
- In FPGAs, LUTs implement small truth tables directly; map your logic to fit LUT inputs
