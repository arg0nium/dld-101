# Counters

Counters are the “odometer” of digital systems. They tick up (or down) every clock and drive timing, indexing, and control.

---

## Basics

- **Up counter**: increments each clock
- **Down counter**: decrements each clock
- **Modulo‑N**: wraps after N−1 back to 0

### Anatomy of an Up Counter
- Register stores current count
- Adder computes next = current + 1
- Reset initializes to 0 (sync or async)

### Exercise
- Draw a block diagram for a 4‑bit synchronous up counter with synchronous reset.

---

## Intermediate

### Ripple vs Synchronous
- Ripple (async): each stage toggles the next; simple but accumulates delay
- Synchronous: all flops share the clock; predictable timing

### Up/Down with Enable
- Add an enable to pause counting; add direction to select +1/−1

### Mod‑N Counters
- Compare with N−1 and reset to 0, or design with tailored next‑state logic

### Exercise
- Design a mod‑10 BCD counter: what extra logic is needed?

---

## Advanced

### Clock Division
- Use counters to derive slower clocks or strobes (prefer strobes in FPGAs)

### Gray Code Counters
- Only one bit changes per step; great for minimizing glitches across domains

### Performance Tips
- Keep the carry chain short; split wide counters or pipeline
- Use vendor primitives for fast adders/counters when available

### Exercise
- Propose a Gray‑code counter for an async FIFO pointer and explain why it’s safer.

---

## Design Notes
- Prefer synchronous resets; register outputs driving heavy fan‑out nets
- In FPGAs, map counters to dedicated carry chains for best timing
