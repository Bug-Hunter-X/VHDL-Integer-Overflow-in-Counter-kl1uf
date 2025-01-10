# VHDL Integer Overflow Bug

This repository demonstrates a subtle integer overflow bug in a simple VHDL counter. The counter is designed to count from 0 to 15, but due to the lack of explicit overflow handling, it wraps around silently when it reaches its maximum value.

## Bug Description
The `buggy_counter.vhd` file contains a VHDL entity and architecture that implement a counter.  The counter increments on each rising edge of the clock signal, but it doesn't handle the case where the counter reaches its maximum value (15). When this occurs, the counter silently wraps around to 0, leading to incorrect output.

## Bug Solution
The `fixed_counter.vhd` file provides a corrected implementation.  The solution involves explicitly checking if the counter has reached the maximum value before incrementing.  If it has, the counter is reset to 0, preventing the overflow.

## How to Reproduce
1. Simulate `buggy_counter.vhd` using a VHDL simulator (such as ModelSim or GHDL).
2. Observe that the counter wraps around from 15 to 0 without any error messages.
3. Simulate `fixed_counter.vhd`.  The counter will now correctly stop at 15.
