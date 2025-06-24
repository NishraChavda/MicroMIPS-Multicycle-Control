# MicroMIPS Multicycle Control Unit

This project implements the **control section of a multicycle datapath for a MicroMIPS processor** in Verilog. The control logic is designed using a **finite state machine (FSM)** to handle various instruction stages like instruction fetch, decode, execution, memory access, and write-back.

---

## Features

- RTL implementation in Verilog
- FSM-based control logic (9 states)
- Supports key instructions:
  - `lw`, `sw` (Load/Store)
  - `j`, `jal`, `jr` (Jump, Jump and Link, Jump Register)
  - `beq`, `bne`, `bltz` (Branches)
  - `add`, `sub`, `R-type` operations
- Synchronous reset and clocked state transitions

---

## Module Interface

### Inputs:
- `clk`, `reset`: Clock and Reset
- `opcode[5:0]`, `funct[5:0]`: Instruction fields

### Outputs:
- Control signals: `MemRead`, `MemWrite`, `RegWrite`, `PCWrite`, etc.
- ALU and register control: `ALUSrcX`, `ALUSrcY`, `ALUFunc`, `RegDst`, etc.
![image](https://github.com/user-attachments/assets/542eaae5-c556-4340-9efa-7c7c94a61e0b)

---

## FSM States

| State     | Operation             |
|-----------|------------------------|
| STATE_0   | Instruction Fetch      |
| STATE_1   | Instruction Decode     |
| STATE_2   | Address Calculation    |
| STATE_3   | Memory Read            |
| STATE_4   | Write Back (load)      |
| STATE_5   | Branch/Jump Execution  |
| STATE_6   | Memory Write (store)   |
| STATE_7   | ALU Execution          |
| STATE_8   | ALU Write Back         |

---
![image](https://github.com/user-attachments/assets/0cb98665-57f8-437a-ac43-0042c0956131)

![image](https://github.com/user-attachments/assets/1e20d391-9e4b-46a5-b019-b09ed78b2b29)




