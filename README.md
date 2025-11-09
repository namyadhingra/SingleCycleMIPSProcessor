# Single Cycle MIPS Processor

An implementation of a **Single-Cycle MIPS Processor** on Logisim, supporting arithmetic, memory, logical, and branching instructions.  
The project demonstrates a complete design flow, from instruction execution and control unit design to simulation and verification using test programs.

---

## 🧠 Overview

This processor executes one instruction per clock cycle following the **MIPS32** architecture.  
It includes fully functional **ALU**, **register file**, **data memory**, **instruction memory**, and **control logic**, integrated within a single-cycle datapath.

The design was developed and simulated in **Xilinx Vivado**, with program instructions loaded via `.hex` files generated from **MARS (MIPS Assembler and Runtime Simulator)**.

---

## ⚙️ Features

- Implements a **Single-Cycle MIPS** architecture
- Supports the following instruction types:
  - **R-type**: `add`, `sub`, `and`, `or`, `slt`
  - **I-type**: `addi`, `lw`, `sw`, `beq`
- **Program Counter (PC)** updates per instruction
- Integrated **Control Unit**, **ALU Control**, and **Branch Logic**
- **Instruction and Data Memory** modules with 32-bit word addressing
- Fully verified through multiple **test programs**

---

## 🧩 Architecture Overview

Core components:
- **ALU** — performs arithmetic and logical operations
- **Register File** — 32 general-purpose registers
- **Control Unit** — decodes opcodes and manages control signals
- **Instruction Memory** — stores program machine code
- **Data Memory** — simulates load/store operations
- **MUX and Sign-Extend Units** — used for control flow and immediate operations

---

## 🧪 Test Programs

Three MIPS assembly test programs were created, assembled in **MARS**, and exported as `.hex` files to verify processor functionality.

| Test | Focus | Key Instructions | Expected Output |
|------|--------|------------------|-----------------|
| **Test 1** | Arithmetic + Memory | `addi`, `add`, `sub`, `lw`, `sw` | Computes `(A + B) - C`, stores result in memory |
| **Test 2** | Logical + Branching | `slt`, `beq`, `and`, `or` | Tests comparison and conditional logic |
| **Test 3** | Loop + Summation | `addi`, `add`, `beq` | Computes the sum `1 + 2 + 3` using a loop |

Each program’s `.hex` file is loaded into **Instruction Memory** for simulation.  
The processor executes until it reaches a `halt` loop (`beq $zero, $zero, halt`).

---

## 🧾 Repository Structure

