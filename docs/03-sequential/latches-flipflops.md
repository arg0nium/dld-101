# Latches & Flip-Flops

Memory for bits! Sequential circuits remember state. Latches and flip-flops are the tiny timekeepers that make counters, registers, and CPUs possible.

---

## Basics

- **Latch (level-sensitive)**: follows input while enable is active
- **Flip-Flop (edge-triggered)**: captures input only on a clock edge (↑ or ↓)
- **D flip-flop**: most common; Q ← D on clock edge

### Small Builds
- 1-bit register = D flip-flop
- N-bit register = N parallel D flip-flops

### Exercise
- When would a latch cause unintended transparency?

---

## Intermediate

### The RS Latch (concept)
- Inputs: S (set), R (reset)
- Output: Q stores a bit
- Caveat: avoid S=R=1 in basic SR latch

### D Flip-Flop with Reset
- Async reset: acts immediately
- Sync reset: acts on clock edge; preferred for FPGA timing

### Setup/Hold Times
- Setup: D must be stable before clock edge
- Hold: D must stay stable after clock edge
- Violations → metastability (indeterminate Q for a short time)

### Exercise
- Explain why synchronizers use two flip-flops for asynchronous inputs.

---

## Advanced

### Clocking Strategies
- Single‑clock synchronous design is simplest and most robust
- Clock enables gate updates without creating new clock domains

### CDC (Clock Domain Crossing)
- Use 2‑FF synchronizers for single‑bit signals
- Use FIFOs or handshakes for multi‑bit data

### Retiming & Pipelining
- Move registers to balance path delays and increase clock frequency

### Exercise
- Given a long combinational block, show where to insert a pipeline register to meet a 100 MHz target.

---

## Design Notes
- Register I/Os at boundaries to localize timing
- Prefer synchronous resets; avoid gated clocks unless using vendor primitives
