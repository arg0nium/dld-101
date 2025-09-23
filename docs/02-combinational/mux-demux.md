# Multiplexers (MUX) & Demultiplexers (DEMUX)

Think of a MUX as a traffic cop for bits—selecting which input gets through. A DEMUX does the opposite: one input, many destinations.

---

## Basics

### MUX
- Inputs: multiple data lines
- Select: control bits choose the active input
- Output: the chosen data line

2:1 MUX equation:
```
Y = S'·D0 + S·D1
```

### DEMUX
- Input: single data line
- Select: control bits choose the active output
- Outputs: one line is asserted at a time

### Exercise
- Write the truth table for a 2:1 MUX.

---

## Intermediate

### 4:1 MUX from 2:1 building blocks
- Cascade 2:1s and add a second select bit

### Select Encoding
- For N inputs, need ⌈log2 N⌉ select lines

### Common Uses
- Choose ALU operands
- Route bus signals
- Implement function select (e.g., ALU opcode → MUX tree)

### Exercise
- Design a 4:1 MUX with inputs A,B,C,D and selects S1,S0. Write Y in SOP form.

---

## Advanced

### Performance Notes
- Large MUXes as trees (log depth) vs flat (wide) implementations
- Balance paths to minimize skew and glitches
- In FPGAs, MUXes map efficiently to LUTs and dedicated MUX primitives

### DEMUX Design Tips
- Ensure only one output is active; use one‑hot decoding
- Combine with enable signals for bus write selection

### Exercise
- Build an 8:1 MUX using 2:1 cells. What’s the logic depth? How many cells?

---

## Design Notes
- Prefer hierarchical construction (2:1 → 4:1 → 8:1)
- Gate‑count vs delay trade‑offs matter in timing‑critical paths
