# VMIPS Simulator Project

## Project Overview
This project implements a **functional and timing simulator** for a vector microarchitecture inspired by VMIPS. The simulator processes vectorized assembly code to model real-world applications such as neural networks and digital signal processing tasks.

## Assembly Test Programs
Three test programs were implemented to validate the simulators:
1. **Fully Connected Layer:** A 256-vector by 256x256 matrix multiplication to simulate a neural network layer.
2. **2D Convolution Layer:** A convolution operation on a **256x256 input frame** using a **3x3 kernel** with zero padding and a stride of 2.
3. **128-point FFT:** Simulates a **128-point FFT** with precomputed Twiddle factors stored in **VDMEM** for signal processing.

## Simulator Implementation
### Functional Simulator:
- Simulates the execution of vector assembly instructions and tracks the final state of registers and memory.
- Handles various memory operations such as load/store, scatter/gather, and vector arithmetic.
- Inputs include:
  - `Code.asm`: The assembly code.
  - `SDMEM.txt`: The initial state of scalar data memory.
  - `VDMEM.txt`: The initial state of vector data memory.

### Timing Simulator:
- Abstracts cycle-by-cycle execution, focusing on the timing for fetching, decoding, and dispatching instructions.
- Simulates how various microarchitectural configurations (e.g., number of lanes, memory banks) affect performance.

## Usage Instructions
To perform the timing simulation, run driver.py file to generate the result.  
To perform the design space analysis, run designSpaceAnalysis.py to generate the result.

**Note:** 
1. **SDMEM.txt, VDMEM.txt, Code.asm, functionalSimulator.py and timingSimulator.py must be in the same directory as the driver.py file.**
2. **The output of the functionalSimulator.py is the input of the timingSimulator.py file**

The instruction files and sample inputs for dot product, fully connected, convolution and fast fourier transforms are also given in the inputs directory. 
To run the functions, the respective input files must be copied to the main directory.
