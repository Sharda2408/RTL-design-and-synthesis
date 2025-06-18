# Day 1: Introduction to Verilog RTL Design and Synthesis

This document summarizes the learning outcomes and labs from Day 1 of the RTL Design and Synthesis Workshop using SKY130 PDK.

📚 Topics Covered

- Introduction to Verilog and RTL Design
- Simulation using Icarus Verilog (iverilog) and GTKWave
- Writing and testing combinational logic using Verilog

---

## 1️⃣ Introduction to Verilog and RTL Design

**Sessions Covered:**
- 01-SKY130RTL D1SK1 L1 Basic Gate Level RTL Design
- 02-SKY130RTL D1SK1 L2 Lab1 Getting Started with Yosys
- 03-SKY130RTL D1SK1 L3 Verilog Introduction
- 04-SKY130RTL D1SK1 L4 Mux Design and Testbench

**Summary:**
Verilog is a hardware description language used to model digital systems. RTL (Register Transfer Level) design involves describing the flow of signals between registers and the logic that processes those signals.

### Key Concepts:
- Module definition and instantiation
- Inputs, outputs, and wire declarations
- Always blocks for combinational and sequential logic
- Testbenches for simulation
- Waveform analysis using GTKWave

---

## 2️⃣ Verilog Code Example - 2:1 Multiplexer

**Design Module:**
```verilog
module mux2x1 (input a, input b, input sel, output y);
  assign y = sel ? b : a;
endmodule
