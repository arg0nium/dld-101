# What is Digital Logic & Design?

Welcome! If computers had a native language, digital logic would be the grammar. We build everything—from adders to CPUs—using simple building blocks that only know two moods: 0 and 1. Moody? Maybe. Powerful? Absolutely.

---

## Basics

- Digital signals are binary: 0 (low) or 1 (high)
- Two categories of circuits:
  - **Combinational**: outputs depend only on current inputs
  - **Sequential**: outputs depend on inputs + stored state
- We describe and build hardware with **Boolean algebra** and **HDLs** (e.g., Verilog)

### Example
- Light controller: output = ON if motion OR (timer active)
- That’s simply: `Light = Motion + Timer`

### Exercise
- Write a Boolean expression for a door alarm that triggers when (door open AND not disarmed) OR (tamper sensor).

---

## Intermediate

- Composition: modules connect to form systems (e.g., adder → ALU → CPU)
- Cost metrics: area (gates), delay (critical path), power, and reliability
- Design flow: spec → truth table/equations → simplification → implementation → test

### Example
- From behavior to logic: “odd parity detector” → XOR all bits → 1 if odd number of 1s

### Exercise
- List three ways to reduce delay in a combinational path. Hint: balance logic, pipeline, minimize fan-out.

---

## Advanced

- Timing closure: meeting setup/hold times across the whole chip
- FSMs for control, datapaths for arithmetic; microarchitectural trade-offs
- HDL to silicon: simulation → synthesis → place & route → timing analysis

### Example
- CPU pipeline hazards (control/data) are solved with forwarding, stall, or speculation—implemented with logic and state machines.

### Exercise
- Sketch a high-level block diagram for a tiny CPU datapath: registers, ALU, MUXes, control FSM.

---

## Learning Flow

1. Number systems and Boolean algebra
2. Combinational building blocks
3. Sequential circuits and state machines
4. Verilog basics and mini-projects

You bring curiosity; we’ll bring the circuits.
