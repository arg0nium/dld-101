# Projects

Apply what you’ve learned with compact, real-world flavored builds. Each project includes a sketch, a truth table or state diagram, and a bite-sized Verilog module.

---

## Beginner

- **Traffic Light Controller (FSM)**
  - Inputs: timer tick, pedestrian button
  - Outputs: lights (R/Y/G)
  - Skills: state diagram, synchronous updates
- **Binary Counter with 7‑Segment Display**
  - Drive common‑anode/cathode display, multiplex digits
  - Skills: counters, decoders, timing

## Intermediate

- **Vending Machine (FSM)**
  - Inputs: coin values, select, cancel
  - Outputs: vend, change, display
  - Skills: Mealy/Moore FSMs, modular design
- **Simple ALU**
  - Ops: add, sub, AND, OR, XOR, shift
  - Skills: datapath MUXing, opcode decoding

## Advanced

- **UART Tx/Rx**
  - Baud generator, framing, oversampling
  - Skills: CDC, timing, verification
- **Tiny CPU (Toy ISA)**
  - Register file, ALU, control FSM, instruction memory
  - Skills: microarchitecture, integration, testing

---

## How to Approach Projects

1. Define I/O and timing behavior
2. Draw block diagram and (if needed) state diagram
3. Build and simulate modules bottom‑up
4. Integrate and add self‑checking tests

> Tip: Keep a log of test vectors and bugs. Future‑you will say thanks.

---

## Next Steps

- Add a `/projects/<name>` page for each build with requirements, diagrams, and testbenches
- Consider a top‑level `sim/` folder for reusable test utilities
