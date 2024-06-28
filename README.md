# Project Title: Design of a 512-bit Array Processor for Integer Arithmetic

## Tools

In this section, you should mention the hardware or simulators utilized in your project.

- Verilog
- ModelSim (for simulation)
- FPGA (for hardware implementation, if applicable)

## Implementation Details

The implementation of the 512-bit array processor includes three primary components: the Register File, the Memory, and the ALU (Arithmetic Logic Unit).

### Register File

The Register File module is responsible for storing and retrieving four 512-bit arrays, named A1 to A4. These registers are updated on the positive edge of the clock signal. The Register File allows efficient storage and retrieval of large data arrays necessary for the processor's operations.

### Memory

The Memory module is designed with a depth of 512 and a width of 32 bits, simulating a memory structure that can load and store 16 consecutive memory locations. This module supports data transfer between the memory and the registers, enabling the processor to handle larger datasets efficiently.

### ALU (Arithmetic Logic Unit)

The ALU module performs the core arithmetic operations of the processor. It supports both multiplication and addition of 512-bit arrays. Based on a control signal, the ALU decides whether to perform addition or multiplication. The results of these operations are divided into a low part and a high part, which are stored in the registers A3 and A4, respectively.

### Processor

The Processor module integrates the Register File, Memory, and ALU, controlling the data flow between these components. It manages the operations based on various control signals, ensuring that data is correctly transferred, processed, and stored. The processor also handles the loading of data from memory to registers and the storing of results back to memory, maintaining the data integrity throughout the operations.

This structured approach ensures that the processor can handle complex arithmetic operations on large data sets efficiently and accurately. By simulating the design with tools like ModelSim, the functionality of the processor can be verified before implementing it on hardware such as an FPGA.

## How to Run

To run the application, use a Verilog simulator such as ModelSim or an FPGA development board to implement the design. The testbench provided can be used to simulate the processor's behavior and verify its functionality.

1. Load the Verilog files into your simulation environment.
2. Run the simulation and observe the output.
3. For hardware implementation, synthesize the design and upload it to an FPGA.

## Results

After successfully running the simulation, the following outputs can be observed:

1. Data transfer between memory and registers.
2. Correct results from addition and multiplication operations.
3. Verification of data transfer from registers back to memory.

## Related Links

- [Verilog](https://en.wikipedia.org/wiki/Verilog)
- [ModelSim](https://www.mentor.com/products/fv/modelsim/)
- [FPGA](https://en.wikipedia.org/wiki/Field-programmable_gate_array)

## Authors

- Ali Salesi
- Ali Pasha Montaseri
- Kamyar Kazari
