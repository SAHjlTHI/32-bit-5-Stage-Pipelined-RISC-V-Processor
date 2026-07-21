# Design and Implementation of a 32-bit 5-Stage Pipelined RISC-V Embedded Processor

## 📖 Overview

This project presents the **Design and Implementation of a 32-bit 5-Stage Pipelined RISC-V Embedded Processor** using **Verilog HDL**. The processor is based on the **RISC-V RV32I Instruction Set Architecture (ISA)** and is designed with a five-stage pipeline consisting of **Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write Back (WB)** stages.

The processor is developed using a modular RTL approach, where each hardware block is implemented as an independent Verilog module. Major components include the **Program Counter (PC), Instruction Memory, Register File, ALU, ALU Control Unit, Control Unit, Data Memory, Forwarding Unit, and Hazard Detection Unit**.

To improve processor performance, the design implements **data forwarding** and **hazard detection** techniques, reducing pipeline stalls and efficiently handling data hazards. The complete design was simulated, synthesized, and implemented using **Xilinx Vivado**, and the functionality was verified through behavioral simulation waveforms, RTL schematics, synthesis reports, implementation reports, power analysis, and resource utilization.

This project provides practical knowledge of **Computer Architecture, Processor Design, RTL Design, FPGA Design, Embedded Systems, and VLSI** concepts.

## 🎯 Objectives

- Design a **32-bit RISC-V (RV32I) Embedded Processor** using Verilog HDL.
- Implement a **5-stage pipelined architecture** to improve processor performance.
- Design all processor modules using a modular RTL approach.
- Develop the Program Counter, Instruction Memory, Register File, ALU, ALU Control Unit, Control Unit, Data Memory, Forwarding Unit, and Hazard Detection Unit.
- Reduce pipeline hazards using forwarding and hazard detection techniques.
- Verify processor functionality using behavioral simulation.
- Generate RTL, synthesis, implementation, and power analysis reports using Xilinx Vivado.
- Gain practical knowledge of processor architecture and hardware design.

## ✨ Key Features

- ✅ 32-bit RISC-V (RV32I) Processor
- ✅ Five-Stage Pipeline Architecture (IF, ID, EX, MEM, WB)
- ✅ Verilog HDL RTL Design
- ✅ Modular Processor Architecture
- ✅ Arithmetic and Logical Operations
- ✅ ALU Control Unit
- ✅ Register File
- ✅ Program Counter
- ✅ Instruction Memory
- ✅ Data Memory
- ✅ Forwarding Unit
- ✅ Hazard Detection Unit
- ✅ Behavioral Simulation
- ✅ RTL Schematic Generation
- ✅ Synthesis and Implementation
- ✅ Power Analysis
- ✅ Resource Utilization Analysis
- ✅ Developed using Xilinx Vivado

## 🛠️ Technology Stack

| Category | Technology |
|----------|------------|
| Hardware Description Language | Verilog HDL |
| Processor Architecture | RISC-V RV32I |
| Design Methodology | RTL Design |
| Development Tool | Xilinx Vivado |
| Simulation | Behavioral Simulation |
| Verification | Verilog Testbench |
| Target Platform | FPGA |

# 🏗️ Project Architecture

The processor is designed based on the **32-bit RISC-V RV32I Instruction Set Architecture (ISA)** using a **5-stage pipelined architecture**. Each stage performs a specific task, allowing multiple instructions to be executed simultaneously. This improves processor throughput and overall performance.

The processor consists of several hardware modules including the **Program Counter, Instruction Memory, Control Unit, Register File, ALU, ALU Control Unit, Data Memory, Forwarding Unit, and Hazard Detection Unit**. These modules work together to fetch, decode, execute, access memory, and write back the results of each instruction.
### Basic Architecture Block Diagram

<img width="833" height="360" alt="image" src="https://github.com/user-attachments/assets/960a47e7-1dde-4257-9a26-dab4102bec66" />

# 🔄 Pipeline Stages

The processor follows a **5-stage pipelined architecture**, where each stage performs a dedicated function.

### 1️⃣ Instruction Fetch (IF)

- Fetches the instruction from Instruction Memory.
- Uses the Program Counter (PC) to access the next instruction.
- Updates the Program Counter for the next clock cycle.

### 2️⃣ Instruction Decode (ID)

- Decodes the fetched instruction.
- Reads source operands from the Register File.
- Generates control signals using the Control Unit.
- Detects hazards using the Hazard Detection Unit.
- 
- ### 📍Register file(screenshot from vivado xilinx)
- Contains 32 general-purpose registers (x0–x31). It reads source operands and stores the final result during the Write Back stage.
 
- <img width="539" height="1011" alt="image" src="https://github.com/user-attachments/assets/f09208df-e358-4a2c-ac5f-6b4349b4d2e9" />

### 📍Control Unit(screenshot from vivado xilinx)
Generates the required control signals based on the instruction opcode for proper execution of instructions.

<img width="685" height="899" alt="image" src="https://github.com/user-attachments/assets/0cb98cc1-6a62-4a25-879e-68f812c4ed05" />

### 📍Hazard Detection Unit(screenshot from vivado xilinx)
-Detects pipeline hazards and inserts stalls whenever forwarding alone cannot resolve the hazard.

<img width="1726" height="570" alt="image" src="https://github.com/user-attachments/assets/6618588e-3b74-4617-9212-582db5866fc0" />

### 3️⃣ Execute (EX)

- Performs arithmetic and logical operations using the ALU.
- ALU operation is selected using the ALU Control Unit.
- Calculates branch addresses.
- Resolves data hazards using the Forwarding Unit.
  
- ### 📍ALU control (screenshot from vivado xilinx)
- Performs arithmetic and logical operations such as ADD, SUB, AND, OR, and other supported RV32I operations.
- Generates ALU control signals using **ALUOp**, **funct3**, and **funct7** fields to determine the required operation.

- <img width="1769" height="438" alt="image" src="https://github.com/user-attachments/assets/d907cab4-a307-4dbf-bfc5-1b6a2dac35b3" />

### 📍Forwarding Unit (screenshot from vivado xilinx)
-Detects data dependencies and forwards data from later pipeline stages to the Execute stage, reducing pipeline stalls.

<img width="1818" height="457" alt="image" src="https://github.com/user-attachments/assets/ade6c0e0-e102-441c-af42-4c42042f3053" />

### 4️⃣ Memory Access (MEM)

- Performs load and store operations.
- Reads from or writes to Data Memory.
- Passes the data to the next stage.
### 📍Data Memory  (screenshot from vivado xilinx)
-Stores data used by load and store instructions during the Memory Access stage.

<img width="1758" height="460" alt="image" src="https://github.com/user-attachments/assets/9019288a-5cb1-49b8-b8ee-011f3f8c95fd" />

### 5️⃣ Write Back (WB)

- Writes the final result back into the Register File.
- Completes the execution of the instruction.

## 📍 Testbench

The testbench is used to verify the functionality of the processor by applying different test cases and observing simulation waveforms. It helps validate the correctness of the processor without modifying the main design.

---
