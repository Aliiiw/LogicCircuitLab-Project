# Logic Circuit Lab Project

Logic Circuit Lab Project is a Proteus/ISIS digital logic design project for a logic circuits course. The repository contains schematic simulation files for three lab tasks: a 4-bit calculator/ALU, a digital clock, and a name-display block built with segment logic.

The project is hardware-schematic based. There is no programming source code in this repository; the main artifacts are Proteus design files.

## Project Parts

| Part | File | Description |
| --- | --- | --- |
| Part 1 | `Project_AliRahimi/AliRahimiProject_Part1.DSN` | Calculator / ALU schematic. |
| Part 2 | `Project_AliRahimi/AliRahimiProjectPart2.pdsprj` | Clock and name-block Proteus project. |

## Features

- Proteus ISIS schematic designs
- 4-bit calculator / ALU
- Add, subtract, multiply, and divide operations
- 2-bit operation selector
- 8-bit result output bus
- Carry, zero, sign, and overflow flags
- Six-digit digital clock design
- Separate counters for seconds, minutes, and hours
- Binary-to-BCD conversion blocks for seven-segment output
- Name-display block using segment-based timing logic
- Digital gates, multiplexers, full adders, JK flip-flops, probes, and logic-state inputs

## Repository Structure

```text
.
+-- README.md
+-- Project_AliRahimi/
|   +-- AliRahimiProject_Part1.DSN
|   +-- AliRahimiProjectPart2.pdsprj
```

## Part 1: Calculator / ALU

`AliRahimiProject_Part1.DSN` contains the calculator circuit. The design acts like a small arithmetic logic unit with two 4-bit inputs and a 2-bit selector.

### Inputs

| Input | Purpose |
| --- | --- |
| `A0` to `A3` | First 4-bit operand. |
| `B0` to `B3` | Second 4-bit operand. |
| `SELECTOR1`, `SELECTOR2` | Select the arithmetic operation. |

### Outputs

| Output | Purpose |
| --- | --- |
| `y0` to `y7` | 8-bit operation result. |
| `CF` | Carry flag. |
| `ZF` | Zero flag. |
| `SF` | Sign flag. |
| `OF` | Overflow flag. |

### Implemented Operation Blocks

The schematic includes these main subcircuits and reusable blocks:

| Block | Purpose |
| --- | --- |
| `ADDER` / `ADDERP` | Addition path. |
| `SUB` / `SUBP` | Subtraction path. |
| `MUL` / `MULP` | Multiplication path. |
| `DIVIDER` / `DIVIDERP` | Division path. |
| `MUX1`, `MUX 2` ... `MUX 12` | Selects the correct operation result and flags. |
| `FULL ADDER` blocks | Bit-level addition building blocks. |
| `BUFFER` | Output buffering / routing block. |

According to the lab specification, operands are treated as two's complement values for add, subtract, and multiply. For division, operands are treated as unsigned values, and the output bus represents the division result and remainder format defined by the assignment.

## Part 2: Clock

`AliRahimiProjectPart2.pdsprj` is a Proteus project archive. It contains a `ROOT.DSN`, component database, and project metadata.

The extracted design metadata shows these main clock blocks:

| Block | Purpose |
| --- | --- |
| `CLOCK` | Main clock circuit. |
| `COUNTER 1 SECOND` | Ones digit of seconds. |
| `COUNTER 2 SECOND` | Tens digit of seconds. |
| `COUNTER 1 MINUTE` | Ones digit of minutes. |
| `COUNTER 2 MINUTE` | Tens digit of minutes. |
| `COUNTER 1 HOUR` | Ones digit of hours. |
| `COUNTER 2 HOUR` | Tens digit of hours. |
| `BINARY TO BCD SECOND` | Converts second counters for display. |
| `BINARY TO BCD MINUTE` | Converts minute counters for display. |
| `BINARY TO BCD HOUR` | Converts hour counters for display. |

The clock is designed for six seven-segment displays, representing hours, minutes, and seconds. The design includes set/reset inputs and counter logic built around digital gates and JK flip-flops.

## Part 3: Name Block

The assignment also includes a name-display block. The intended behavior is:

1. All segments start turned off.
2. After five seconds, the first letter appears.
3. The sequence continues until every letter is displayed.
4. After the full name is visible, the display blinks until the end of the day.

This part is included with the Proteus schematic project rather than as source code.

## Tools and Technologies

- Proteus ISIS / Proteus Design Suite
- Digital logic gates: AND, OR, NOT, XOR, NOR
- Multiplexers
- Full adders
- JK flip-flops
- Logic states and logic probes
- BCD and seven-segment display components

## How to Open

1. Install Proteus Design Suite. The project metadata indicates a Proteus 8.x design format.
2. Open the ALU design:

```text
Project_AliRahimi/AliRahimiProject_Part1.DSN
```

3. Open the clock/name-block project:

```text
Project_AliRahimi/AliRahimiProjectPart2.pdsprj
```

4. Run the simulation from Proteus and change logic-state inputs to test different cases.

## How to Test the ALU

1. Open `AliRahimiProject_Part1.DSN` in Proteus.
2. Set `A0` to `A3` for the first operand.
3. Set `B0` to `B3` for the second operand.
4. Change `SELECTOR1` and `SELECTOR2` to choose the operation.
5. Read the result from `y0` to `y7`.
6. Check `CF`, `ZF`, `SF`, and `OF` for status flags.

## How to Test the Clock

1. Open `AliRahimiProjectPart2.pdsprj` in Proteus.
2. Run the simulation.
3. Use the binary set inputs for hour, minute, and second values.
4. Watch the six seven-segment displays continue counting from the selected start time.

## Notes

- The repository stores compiled Proteus schematic artifacts, not plain text source files.
- `.pdsprj` is a Proteus project archive containing internal files such as `ROOT.DSN`, `ROOT.CDB`, and `PROJECT.XML`.
- The design uses many hierarchical subcircuits, which makes it easier to inspect each arithmetic or counter block independently in Proteus.
- A `.DS_Store` file is present in the repository and is not required for the Proteus project.

## Possible Improvements

- Add screenshots of each schematic page
- Add a truth table for the ALU selector modes
- Document exact flag behavior for each operation
- Add sample test cases for add, subtract, multiply, and divide
- Add screenshots or waveform captures for the clock
- Remove OS-specific files such as `.DS_Store`
- Export schematic pages as PDFs for easier viewing without Proteus
