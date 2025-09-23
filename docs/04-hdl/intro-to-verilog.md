# Intro to Verilog (HDL)

Verilog lets you describe hardware like code—but it becomes circuits, not software. Write modules, connect wires, simulate, and then synthesize to real logic.

---

## Basics

### Mental Model
- You’re building hardware structures, not writing sequential programs
- Many things happen “at once” (concurrency!)
- Registers (flops) remember; wires combine

### Tiny Taste
```verilog
module and_gate(
  input  wire a,
  input  wire b,
  output wire y
);
  assign y = a & b;
endmodule
```

### Exercise
- Write a `or_gate` module using a continuous assignment.

---

## Intermediate

### Sequential vs Combinational Blocks
```verilog
// Combinational
always @* begin
  y = (a ^ b) & c; // blocking for comb
end

// Sequential
always @(posedge clk) begin
  if (rst) q <= 1'b0; // non-blocking for flops
  else     q <= d;
end
```

### Parameters & Generate
```verilog
module regn #(parameter N=8) (
  input  wire         clk,
  input  wire [N-1:0] d,
  output reg  [N-1:0] q
);
  always @(posedge clk) q <= d;
endmodule
```

```verilog
// Generate an array of adders
for (genvar i=0; i<8; i=i+1) begin : add_loop
  assign sum[i] = a[i] ^ b[i] ^ cin[i];
end
```

### Simple Testbench
```verilog
module tb_and;
  reg a, b; wire y;
  and_gate dut(.a(a), .b(b), .y(y));
  initial begin
    a=0; b=0; #1; a=0; b=1; #1; a=1; b=0; #1; a=1; b=1; #1;
  end
endmodule
```

### Exercise
- Parameterize a 4‑bit adder to N bits and simulate with a few vectors.

---

## Advanced

### Coding Patterns
- One purpose per `always` block (comb vs seq)
- Default assignments in comb blocks to avoid latches
- Register outputs crossing module boundaries

### FSM Template (One‑Hot)
```verilog
typedef enum logic [2:0] { S0=3'b001, S1=3'b010, S2=3'b100 } state_t;
state_t s, sn;

always @* begin
  sn = s; // default
  unique case (s)
    S0: sn = start ? S1 : S0;
    S1: sn = done  ? S2 : S1;
    S2: sn = S0;
  endcase
end

always @(posedge clk) begin
  if (rst) s <= S0; else s <= sn;
end
```

### Verification Tips
- Self‑checking tests: compare outputs, `$fatal` on mismatch
- Constrain randomize inputs for broader coverage
- View waveforms with GTKWave

### Exercise
- Write a self‑checking testbench for a 2:1 MUX using randomized inputs and an assertion of `y == (s ? d1 : d0)`.

> Remember: HDL describes structure and timing. If it can’t exist in hardware, it shouldn’t be in your Verilog.
