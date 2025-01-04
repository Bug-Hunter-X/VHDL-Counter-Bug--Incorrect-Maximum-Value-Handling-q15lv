# VHDL Counter Bug: Incorrect Maximum Value Handling

This repository demonstrates a common error in VHDL counters: incorrect handling of the maximum count value. The original code (`buggy_counter.vhd`) exhibits this error.  The corrected code (`buggy_counter_fixed.vhd`) provides the solution.

## Bug Description
The `buggy_counter.vhd` module implements a simple 4-bit counter. However, the code does not correctly handle the rollover from the maximum count (15) back to 0.  This leads to an unexpected behavior when the counter reaches its maximum value. 

## Solution
The `buggy_counter_fixed.vhd` addresses the problem by using a `when` statement to explicitly handle the rollover condition instead of relying solely on an `if-else` statement within the process.  This ensures a clean and predictable rollover from 15 back to 0.

## How to Reproduce
1. Simulate `buggy_counter.vhd` using a VHDL simulator (like ModelSim, GHDL, etc.).
2. Observe that the counter does not correctly reset to 0 after reaching the value 15.
3. Simulate `buggy_counter_fixed.vhd` and verify the correct rollover behaviour.