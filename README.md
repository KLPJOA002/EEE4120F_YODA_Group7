# High Performance Embedded Systems EEE4120F YODA Project
### Group 7 Repository

## Overview
YODA is a university project built around Star-Core 1, a theoretical RISC-based CPU architecture designed for use in a CubeSat application. The original Star-Core 1 is a 16-bit word-length processor written in Verilog, provided as a baseline design for the course.

This project extends that baseline in two key areas:
 
1. **Vectorised ALU** — modifying the Arithmetic Logic Unit to support SIMD-style operations on the upper and lower 8-bit halves of the 16-bit word simultaneously.
2. **Memory-Mapped GPIO** — extending the data memory interface to expose General Purpose I/O registers, enabling interaction with FPGA peripherals.

---

## Project Contributions
 
### 1. Vectorised ALU
 
The standard Star-Core 1 ALU treats the full 16-bit word as a single operand. The YODA enhancement splits each 16-bit word into two 8-bit lanes and performs arithmetic/logic operations on **both lanes simultaneously**.
 
This allows a single instruction to compute two independent 8-bit results in parallel — a lightweight form of SIMD (Single Instruction, Multiple Data) suited to the constrained CubeSat context.
 
**Supported vectorised operations include:**
- Addition / Subtraction (upper byte and lower byte independently)
- Bitwise AND / OR / XOR (per lane)
- *(extend this list as applicable to your design)*
### 2. Memory-Mapped GPIO
 
The data memory has been extended to include a **memory-mapped I/O region** that exposes GPIO pins on the FPGA. Software running on the CPU can read from and write to these registers using standard load/store instructions, with no additional hardware instructions required.
 
This makes it straightforward to interface with on-board peripherals such as LEDs, buttons, or sensors connected to the FPGA.

---
## Team
 
| Name | Student Number |
|---|---|
| *Joab Gray Kloppers* | *KLPJOA002* |
| *(Team member)* | *(e.g. GPIO Memory Mapping)* |
| *(Team member)* | *(e.g. Testbench & Verification)* |
 
---
