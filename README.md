# MicroMIPS Multicycle Control Unit

This project implements the **control section of a multicycle datapath for a MicroMIPS processor** in Verilog. The control logic is designed using a **finite state machine (FSM)** to handle various instruction stages like instruction fetch, decode, execution, memory access, and write-back.

---

## 🚀 Features

- RTL implementation in Verilog
- FSM-based control logic (9 states)
- Supports key instructions:
  - `lw`, `sw` (Load/Store)
  - `j`, `jal`, `jr` (Jump, Jump and Link, Jump Register)
  - `beq`, `bne`, `bltz` (Branches)
  - `add`, `sub`, `R-type` operations
- Synchronous reset and clocked state transitions

---

## 🧱 Module Interface

### Inputs:
- `clk`, `reset`: Clock and Reset
- `opcode[5:0]`, `funct[5:0]`: Instruction fields

### Outputs:
- Control signals: `MemRead`, `MemWrite`, `RegWrite`, `PCWrite`, etc.
- ALU and register control: `ALUSrcX`, `ALUSrcY`, `ALUFunc`, `RegDst`, etc.

---

## 📊 FSM States

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

## 🔍 Files

- `control_unit.v`: Main Verilog file (FSM-based control logic)
- `README.md`: Project documentation
- `testbench.v` (optional): Add your testbench for simulation
- `fsm_diagram.png` (optional): Visual diagram of FSM states and transitions

---

## 🛠️ Tools Used

- Verilog HDL
- ModelSim / Vivado / GTKWave (for simulation)
- Git & GitHub

---

## 📷 Demo

> *Add FSM diagram or simulation waveform screenshots here.*

---

## 📚 Reference

- Computer Organization and Design by Patterson & Hennessy
- MIPS and MicroMIPS Architecture Documentation

---

## 👩‍💻 Author

**[Your Name]** – [Your LinkedIn or GitHub profile link]

---

