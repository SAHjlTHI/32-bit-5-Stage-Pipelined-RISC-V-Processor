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

## 📂 Source Code

The complete Verilog HDL source code is available in the `src/` folder.

Main modules include:

- riscv_cpu.v
- alu_8bit.v
- control_unit.v
- alu_control.v
- reg_file.v
- instr_mem.v
- data_mem.v
- forwarding_unit.v
- hazard_detection_unit.v

The simulation testbench is available in the `testbench/` folder.

# 🏗️ Project Architecture

The processor is designed based on the **32-bit RISC-V RV32I Instruction Set Architecture (ISA)** using a **5-stage pipelined architecture**. Each stage performs a specific task, allowing multiple instructions to be executed simultaneously. This improves processor throughput and overall performance.

The processor consists of several hardware modules including the **Program Counter, Instruction Memory, Control Unit, Register File, ALU, ALU Control Unit, Data Memory, Forwarding Unit, and Hazard Detection Unit**. These modules work together to fetch, decode, execute, access memory, and write back the results of each instruction.
### Basic Architecture Block Diagram

<img width="833" height="360" alt="image" src="https://github.com/user-attachments/assets/960a47e7-1dde-4257-9a26-dab4102bec66" />

## 🔄 Design Flow

The processor design follows a modular pipelined architecture where each hardware module works together to execute instructions efficiently.

📷 Data Flow Design(Screen shot from vivado xilinx)

<img width="1874" height="755" alt="image" src="https://github.com/user-attachments/assets/d9f8d1c5-dc8e-4cee-9f8a-c5558eecd6f5" />

## 🔧 Schematic Diagram

The complete processor datapath was generated using Xilinx Vivado. It shows the interconnection of all hardware modules including the Instruction Memory, Register File, Control Unit, ALU, Data Memory, Hazard Detection Unit, and Forwarding Unit.

📷 Schematic Diagram(Screen shot from vivado xilinx)

<img width="1968" height="549" alt="image" src="https://github.com/user-attachments/assets/7f6a05e8-9977-47b0-9811-d392beb0a8f8" />

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
 
- 📷 <img width="539" height="1011" alt="image" src="https://github.com/user-attachments/assets/f09208df-e358-4a2c-ac5f-6b4349b4d2e9" />

### 📍Control Unit(screenshot from vivado xilinx)
Generates the required control signals based on the instruction opcode for proper execution of instructions.

📷 <img width="685" height="899" alt="image" src="https://github.com/user-attachments/assets/0cb98cc1-6a62-4a25-879e-68f812c4ed05" />

### 📍Hazard Detection Unit(screenshot from vivado xilinx)
-Detects pipeline hazards and inserts stalls whenever forwarding alone cannot resolve the hazard.

📷 <img width="1726" height="570" alt="image" src="https://github.com/user-attachments/assets/6618588e-3b74-4617-9212-582db5866fc0" />

### 3️⃣ Execute (EX)

- Performs arithmetic and logical operations using the ALU.
- ALU operation is selected using the ALU Control Unit.
- Calculates branch addresses.
- Resolves data hazards using the Forwarding Unit.
  
- ### 📍ALU control (screenshot from vivado xilinx)
- Performs arithmetic and logical operations such as ADD, SUB, AND, OR, and other supported RV32I operations.
- Generates ALU control signals using **ALUOp**, **funct3**, and **funct7** fields to determine the required operation.

- 📷 <img width="1769" height="438" alt="image" src="https://github.com/user-attachments/assets/d907cab4-a307-4dbf-bfc5-1b6a2dac35b3" />

### 📍Forwarding Unit (screenshot from vivado xilinx)
-Detects data dependencies and forwards data from later pipeline stages to the Execute stage, reducing pipeline stalls.

📷 <img width="1818" height="457" alt="image" src="https://github.com/user-attachments/assets/ade6c0e0-e102-441c-af42-4c42042f3053" />

### 4️⃣ Memory Access (MEM)

- Performs load and store operations.
- Reads from or writes to Data Memory.
- Passes the data to the next stage.
### 📍Data Memory  (screenshot from vivado xilinx)
-Stores data used by load and store instructions during the Memory Access stage.

📷 <img width="1758" height="460" alt="image" src="https://github.com/user-attachments/assets/9019288a-5cb1-49b8-b8ee-011f3f8c95fd" />

### 5️⃣ Write Back (WB)

- Writes the final result back into the Register File.
- Completes the execution of the instruction.

## 📊 Simulation Results

The processor was successfully simulated using Xilinx Vivado 2023.1. RTL simulations verified the functionality of the processor modules, including the Register File, Control Unit, ALU Control Unit, Data Memory, Hazard Detection Unit, and Forwarding Unit.

### 📍 Simulation Waveform

 📷 Functional Simulation Waveform from Vivado
 
 <img width="1809" height="539" alt="image" src="https://github.com/user-attachments/assets/0cafc240-d3fa-48f0-b07f-1ae4178974c0" />

The ALU takes inputs A = 12 (00001100) and B = 10 (00001010) with control signals alu_op = 10, funct3 = 111. 
Based on these signals, the ALU performs a bitwise AND operation. 
The computed output is 00001000 (8 in decimal). 
This verifies correct ALU functionality as per the control logic. 

The simulation confirms the correct execution of arithmetic and logical operations, control signal generation, register updates, and data flow through the processor pipeline.

# ⚡ Power Analysis

Power analysis was performed using **Xilinx Vivado** to estimate the total power consumption of the implemented processor design. The report includes dynamic power, static power, and on-chip resource power consumption, helping evaluate the energy efficiency of the process

### 📍 Vivado Power Analysis report screenshot

📷 <img width="1683" height="499" alt="image" src="https://github.com/user-attachments/assets/41dab127-2e01-401c-a5de-800ae89f5771" />

# 📈 Resource Utilization

Resource utilization analysis was carried out after synthesis and implementation in **Xilinx Vivado**. The report shows the FPGA resources used by the processor, including LUTs, Flip-Flops (FFs), I/O Pins, Block RAM (BRAM), and DSP resources.

### 📍 Vivado Resource Utilization report screenshot 

📷 <img width="1792" height="483" alt="image" src="https://github.com/user-attachments/assets/46f863ff-6d5b-4575-a08b-edacbe96f02b" />

## 🏆 Project Outcome

- Successfully designed a 32-bit RISC-V RV32I Processor.
- Implemented a 5-stage pipelined architecture.
- Reduced pipeline stalls using Forwarding and Hazard Detection Units.
- Verified the processor using RTL simulation in Vivado.
- Developed the processor using modular Verilog HDL design.

## 🌍 Applications

- Embedded Systems
- IoT Devices
- Educational Processor Design
- FPGA-Based Digital Systems
- Computer Architecture Research
- Low-Power Embedded Computing

## 🚀 Future Scope

- Support for complete RV32I Instruction Set
- Branch Prediction Unit
- Instruction & Data Cache
- Interrupt and Exception Handling
- UART, SPI and I2C Peripheral Interfaces
- FPGA Hardware Implementation
- Performance Optimization

  # 📚 References

1. RISC-V International. *The RISC-V Instruction Set Manual (RV32I).*
2. Xilinx. *Vivado Design Suite User Guide.*
3. Samir Palnitkar. *Verilog HDL: A Guide to Digital Design and Synthesis.*
4. David A. Patterson and John L. Hennessy. *Computer Organization and Design: RISC-V Edition.*

## 👩‍💻 Author

**K. Sahithi**

Final Year B.Tech (ECE)

Interested in RTL Design, Digital Design and VLSI

## ⭐ Acknowledgement

This project was developed as part of an academic mini/final year project to understand the implementation of a pipelined RISC-V processor using Verilog HDL and FPGA design tools.
  

## 📍 Testbench

The testbench is used to verify the functionality of the processor by applying different test cases and observing simulation waveforms. It helps validate the correctness of the processor without modifying the main design.
