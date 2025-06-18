Day 2: Timing Libraries, Hierarchical vs Flat Synthesis, and Efficient Flop Coding Styles

This document summarizes the concepts covered on Day 2 of the RTL Design and Synthesis Workshop using SKY130 PDK.

📚 Topics Covered

Introduction to Timing Libraries (.lib)

Hierarchical vs Flat Synthesis

Efficient Flop Coding Styles and Optimizations

1️⃣ Introduction to Timing Libraries (.lib)

Sessions:

10-SKY130RTL D2SK1 L1 Lab4 Introduction to dot Lib part1

11-SKY130RTL D2SK1 L2 Lab4 Introduction to dot Lib part2

12-SKY130RTL D2SK1 L3 Lab4 Introduction to dot Lib part3

Summary:

Timing libraries (.lib files) contain information about delay, power, setup/hold times, and other parameters for standard cells.

The .lib file used: sky130_fd_sc_hd__tt_025C_1v80.lib

Important sections include:

Cell definitions with timing arcs

Pin definitions with input/output delays

Lookup tables for delay calculation

Used during synthesis to estimate timing and guide optimization.

Key Concepts:

Delay modeling: cell rise/fall, net delay, transition time

Setup/Hold constraints and their role in valid timing

The .lib file provides critical information to the synthesis tool to produce accurate gate-level netlists

2️⃣ Hierarchical vs Flat Synthesis

Sessions:

13-SKY130RTL D2SK2 L1 Lab05 Hierarchical synthesis part1

14-SKY130RTL D2SK2 L2 Lab05 Hierarchical synthesis part2

Summary:

Flat Synthesis: All RTL modules are flattened into a single module before synthesis.

Pros: Optimized globally

Cons: Slower, memory-intensive, harder to debug

Hierarchical Synthesis: RTL modules are synthesized independently and then linked.

Pros: Faster, memory-efficient

Cons: Less optimal, boundary optimizations limited

Comparison Table:

Aspect

Flat Synthesis

Hierarchical Synthesis

Optimization Scope

Global

Local per module

Memory Usage

High

Low

Debugging

Complex

Easier

Compilation Time

Slow

Fast

Ideal Use Case

Small/Medium Designs

Large Designs

Command Used:

# For hierarchical synthesis in yosys
synth -top <top_module> -flatten

3️⃣ Various Flop Coding Styles and Optimization

Sessions:

15-SKY130RTL D2SK3 L1 Why Flops and Flop coding styles part1

16-SKY130RTL D2SK3 L2 Why Flops and Flop coding styles part2

17-SKY130RTL D2SK3 L3 Lab flop synthesis simulations part1

18-SKY130RTL D2SK3 L4 Lab flop synthesis simulations part2

19-SKY130RTL D2SK3 L5 Interesting optimizations part1

20-SKY130RTL D2SK3 L6 Interesting optimizations part2

Summary:

Different styles of coding flip-flops in Verilog impact how synthesis tools map RTL to gates.

Common Styles:

Synchronous Reset:

always @(posedge clk) begin
  if (reset) q <= 0;
  else       q <= d;
end

Asynchronous Reset:

always @(posedge clk or posedge reset) begin
  if (reset) q <= 0;
  else       q <= d;
end

Enable Based Flop:

always @(posedge clk) begin
  if (enable) q <= d;
end

Best Practices:

Use async resets for initialization

Prefer non-blocking assignments in sequential always blocks

Avoid latch inference by always using else

Optimization Tips:

Merge flops with enable signals where possible

Remove redundant logic (e.g., reset paths if unused)

Lab Results:

Different coding styles affect:

Area

Timing

Power

✅ Conclusion

Day 2 introduced timing libraries and their role in synthesis, covered structural differences in synthesis strategies, and optimized RTL design using efficient coding practices.

🔗 References

SKY130 .lib documentation

OpenLane GitHub

Workshop repository and labs
