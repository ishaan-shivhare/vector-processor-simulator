# VMIPS Simulator Project

## Project Overview
This project implements a **functional and timing simulator** for a vector microarchitecture inspired by VMIPS. The simulator processes vectorized assembly code to model real-world applications such as neural networks and digital signal processing tasks.

### Key Contributions:
- **Memory Access Optimizations:**  
   Focused on optimizing vector memory access patterns, particularly in the **fully connected layer** and **FFT** test programs. These optimizations minimize memory contention and improve overall performance through techniques like **strided loads** and **scatter-gather** operations.

- **Efficient Convolution Layer Simulation:**  
   Optimized the instruction scheduling and memory access patterns for a **256x256 convolution layer**. These improvements resulted in significant performance boosts in cycle count and memory usage.

- **FFT Precision Handling:**  
   Scaled the Twiddle factors by 1000 to handle precision limitations in the **128-point FFT**, ensuring accurate integer-based computations within the constraints of the VMIPS simulator.

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
### Running the Functional Simulator:
```bash
python <netid>_funcsimulator.py --iodir <path/to/io/files>
