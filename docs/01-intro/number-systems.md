# Number Systems (Binary, Decimal, Hex)

Humans vibe with base-10. Computers throw a party in base-2. Hex shows up as the chill mutual friend. Let’s translate between them without breaking a sweat.

---

## Basics

- Binary (base-2): digits 0–1
- Decimal (base-10): digits 0–9
- Hex (base-16): digits 0–9 + A–F
- Place value: value = sum(digit × base^position)

### Examples
- 13₁₀ = 1101₂
- 10110₂ = 22₁₀
- 1101₂ → group 4 bits → D₁₆

### Exercises
- Convert 45₁₀ to binary and hex
- Convert 1001011₂ to decimal

---

## Intermediate

### Binary ↔ Hex (fast path)
- Group bits in 4s. 1011₂ = B₁₆. 111001₂ = 39₁₆.

### Two’s Complement (Signed Numbers)
1) Write magnitude in binary  2) Invert bits  3) Add 1
- Example: -5 in 4 bits → 0101 → 1010 → 1011₂

### Range
- For n bits: unsigned 0…2ⁿ-1, signed −2ⁿ⁻¹…2ⁿ⁻¹−1

### Exercises
- What’s the 8‑bit two’s complement of −7?
- What is the range of a 12‑bit signed integer?

---

## Advanced

### Overflow
- Unsigned: carry out from MSB
- Signed: adding two same‑sign numbers yields opposite‑sign result

### Fixed‑Point
- Represent fractions by fixing a binary point (e.g., Q1.7)

### Endianness (systems topic)
- Byte order in memory: little vs big endian

### Exercises
- Detect signed overflow for A + B using MSB and carry logic
- Represent 0.625 in Q0.8 fixed‑point and convert back to decimal

> Try small mental chunks: powers of two up to 256 go a long way.
