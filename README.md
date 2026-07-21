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
