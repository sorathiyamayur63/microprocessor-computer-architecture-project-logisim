# Digital Logic & Computer Architecture Projects

A collection of Digital Logic Design and Computer Architecture circuits created using Logisim.

## Overview

This repository contains implementations of fundamental digital circuits used in computer systems. These projects demonstrate the working principles of logic gates, arithmetic circuits, registers, and Arithmetic Logic Units (ALU).

## Contents

| Project | Description |
|----------|------------|
| add.circ | Binary Adder Circuit |
| sub.circ | Binary Subtractor Circuit |
| and.circ | AND Gate Implementation |
| or.circ | OR Gate Implementation |
| xor.circ | XOR Gate Implementation |
| not.circ | NOT Gate Implementation |
| alu.circ | Arithmetic Logic Unit |
| registers_file.circ | Register File Design |
| mp.circ | microP Related Circuit |
| ascii_table.png | ASCII Reference Table |

## Features

- Basic Logic Gates
- Arithmetic Operations
- Register Operations
- ALU Design
- ASCII Character Reference
- Educational and Learning Purpose

## How To Run

### Step 1

Download and install Logisim.


### Step 2

Open `mp.circ` file using Logisim.

### Step 4

Run simulations and observe outputs.

## Memory Mapping (RAM & ROM Configuration)

This project can be modified to support different RAM and ROM sizes by changing the address decoding logic inside the Logisim circuits.

### Default Memory Layout

| Memory Device | Start Address | End Address | Size |
|--------------|--------------|------------|------|
| ROM | 0x0000 | 0x7FFF | 32 KB |
| RAM | 0x8000 | 0xFFFF | 32 KB |

### Changing ROM Mapping

1. Open the circuit in Logisim.
2. Select the ROM component.
3. Change:
   - Address Bit Width
   - Data Bit Width
   - Memory Contents
4. Modify the address decoder to match the new ROM address range.

Example:

```
ROM:
Start = 0x0000
End   = 0x3FFF
Size  = 16 KB
```

## Custom Instruction Set Architecture (ISA)

This project implements a simple 8-bit microprocessor using Logisim.

### Instruction Format


| Opcode | Operand |
|--------|---------|
| 7..4   | 3..0    |
|--------|---------|


- Upper 4 bits → Operation Code
- Lower 4 bits → Operand / Register Selection

---

## Instruction Mapping

| Hex | Binary | Operation |
|------|---------|----------|
| 01 | 0000 0001 | Load Register A |
| 03 | 0000 0011 | Load Register B |
| 04 | 0000 0100 | Output Enable |
| 0B | 0000 1011 | Store ALU Result |
| 10 | 0001 0000 | ADD |
| 30 | 0011 0000 | OR |
| 50 | 0101 0000 | AND |
| 70 | 0111 0000 | XOR |
| B0 | 1011 0000 | NOT |

---

## ALU Operations

Supported operations:

- ADD
- SUB
- AND
- OR
- XOR
- NOT

Operation selection is performed using the ALU control bits generated from the opcode decoder.

---

## Register Organization

Available registers:

- Register A
- Register B
- Register E (ALU Result Register)

### Data Flow

```
Input → Register A
Input → Register B

Register A ----\
                > ALU → Register E → Output
Register B ----/
```

---

## Example Program

### Addition

Load 5 into Register A

```
01 05
```

Load 3 into Register B

```
03 03
```

Execute ADD

```
10
```

Store Result

```
0B
```

Display Output

```
04
```

Output:

```
5 + 3 = 8
```

---

## ROM Programming

Program instructions are stored in ROM.

Example:

| Address | Data |
|----------|------|
| 00 | 01 |
| 01 | 05 |
| 02 | 03 |
| 03 | 03 |
| 04 | 10 |
| 05 | 0B |
| 06 | 04 |

Users can modify ROM contents to create custom programs.

---

## Memory Modification

To change instruction behavior:

1. Open ROM in Logisim.
2. Edit hexadecimal values.
3. Save ROM contents.
4. Run simulation.

The processor will execute instructions according to the updated opcode sequence.

## Educational Purpose

This repository was created for learning and academic practice in:

- Digital Electronics
- Computer Organization
- Computer Architecture
- Microprocessor Fundamentals

## Author

Mayur
