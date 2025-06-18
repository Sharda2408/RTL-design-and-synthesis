# 📘 Day 1 – Introduction to Verilog RTL Design and Synthesis

## 📑 Table of Contents
- [Introduction to Verilog RTL Design and Synthesis](#1-🧠-introduction-to-verilog-rtl-design-and-synthesis)
- [Open-source Simulator iverilog](#2-🛠️-open-source-simulator-iverilog)
  - [How a Simulator Works](#🔍-how-a-simulator-works)
  - [Iverilog-Based Simulation](#⚙️-iverilog-based-simulation)
- [Using iverilog and GTKWave](#3-🧪-using-iverilog-and-gtkwave)
- [Yosys and Logic Synthesis](#4-⚙️-yosys-and-logic-synthesis)
- [Yosys with Sky130 PDKs](#5-🧪-yosys-with-sky130-pdks)
- [✅ Summary](#✅-summary)

---

## 1. 🧠 Introduction to Verilog RTL Design and Synthesis

**Verilog** is a Hardware Description Language (HDL) used to describe and model digital systems.

<<<<<<< HEAD
**RTL (Register Transfer Level)** describes circuits in terms of data flow and registers.
=======
**RTL** (Register Transfer Level) describes circuits in terms of data flow and registers.
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)

**Sequential logic** is modeled using constructs like:

```shell
verilog
always @(posedge clk)
begin
  // logic
end
```
## 2. 🛠️ Open-source Simulator iverilog

<<<<<<< HEAD
### 🔍 How a Simulator Works

-Simulation mimics hardware behavior without fabrication.

-Takes HDL code + testbench → calculates outputs based on stimuli.

-Tracks signal transitions, resolves delays and logic events.
=======
 **How a Simulator Works**
-Simulation mimics hardware behavior without fabrication.

-Takes HDL code + testbench → calculates outputs based on stimuli.

-Tracks signal transitions, resolves delays and logic events

-Outputs a .vcd (Value Change Dump) file for waveform viewing.

>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)

-Outputs a .vcd (Value Change Dump) file for waveform viewing.

<<<<<<< HEAD
### ⚙️ Iverilog-Based Simulation

**Icarus Verilog** (iverilog) is an open-source command-line simulator.

**Compilation flow:**

-Write Verilog design and testbench

-Compile using iverilog

-Run the generated executable

=======
-Compilation flow:

-Write Verilog design and testbench

-Compile using iverilog

-Run the generated executable

>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)
-View output waveform using GTKWave

📷 Image: Simulation process using iverilog

## 3. 🧪 Using iverilog and GTKWave
<<<<<<< HEAD

### ⚙️ Setup
=======
⚙️ Setup
bash
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)
```shell
sudo apt install iverilog gtkwave
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
cd sky130RTLDesignAndSynthesisWorkshop/verilog_files
```
🧩 Simulating a 2:1 Mux Example

**Files Used:**

-good_mux.v – Verilog design

<<<<<<< HEAD
-tb_good_mux.v – Testbench

=======
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)
```shell
iverilog good_mux.v tb_good_mux.v
./a.out
gtkwave tb_good_mux.vcd
```
📷 Image: GTKWave waveform

```shell
gvim tb_good_mux.v -o good_mux.v
```
📷 Image: Verilog code in GVim
<<<<<<< HEAD

**GTKWave** displays signal transitions to verify behavior.

The **testbench** provides clock, stimulus, and resets.

## 4. ⚙️ Yosys and Logic Synthesis

**Yosys** is a synthesis tool that converts Verilog RTL to a gate-level netlist.
=======
```
GTKWave displays signal transitions to verify behavior.
The testbench provides clock, stimulus, and resets.

## 4. ⚙️ Yosys and Logic Synthesis
Yosys is a synthesis tool that converts Verilog RTL to a gate-level netlist.
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)

📷 Image: Yosys interface

📷 Image: Yosys terminal setup

<<<<<<< HEAD
### Synthesis steps:
=======
**Synthesis steps:**
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)

-Parse RTL

-Optimize logic

-Map to technology cells

📷 Image: Logic gate mapping process

### 🧱 Netlist

A **netlist** is a list of gates and their interconnections.

It’s the output of synthesis tools, based on libraries like Sky130.

## 5. 🧪 Yosys with Sky130 PDKs
<<<<<<< HEAD
🧰 Sample Flow
=======
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)
```shell
yosys
read_liberty -lib ./lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog good_mux.v
synth -top good_mux
abc -liberty ./lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
```
📷 Image: Synthesized circuit schematic (Yosys)

### 🧠 Gate-Level Mapping

**Yosys maps logic to standard cells like:**

-AND2_X1 – AND gate with X1 drive strength

-INV_X1 – Inverter with X1 drive strength

-Drive strength suffixes:

-X1: Lower power, smaller size, slower

<<<<<<< HEAD
-X4: Higher power, faster, larger area
=======
## ✅ Summary
Introduced to Verilog and RTL design structure.
>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)

## ✅ Summary
-Introduced to Verilog and RTL design structure.

-Understood simulation concept and how simulators process time-based events.

-Practiced running iverilog and using GTKWave for waveform analysis.

-Synthesized RTL to gate-level netlist using Yosys.

<<<<<<< HEAD
-Explored Sky130 standard cell libraries and drive strength impact.
=======

>>>>>>> 1701d59 (Removed extra folders and typo file, cleaned up repo)
