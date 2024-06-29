# Project Title: Design of a 512-bit Array Processor for Integer Arithmetic

## Tools

- Verilog
- ModelSim (for simulation)
- FPGA (for hardware implementation, if applicable)

## Implementation Details

The implementation of the 512-bit array processor includes three primary components: the Register File, the Memory, and the ALU (Arithmetic Logic Unit).

### Register File

The Register File module is responsible for storing and retrieving four 512-bit arrays, named A1 to A4. These registers are updated on the positive edge of the clock signal. The Register File is implemented as an array of four 512-bit registers. Each register can be accessed and updated based on the clock signal. The Register File allows efficient storage and retrieval of large data arrays necessary for the processor's operations.

### Memory

The Memory module is designed with a depth of 512 and a width of 32 bits, simulating a memory structure that can load and store 16 consecutive memory locations in one operation. The Memory module allows data transfer between the memory and the registers. It supports writing data to memory and reading data from memory, using an address input and a write enable signal. During a write operation, the data input is divided into 32-bit chunks and written to 16 consecutive memory locations. During a read operation, data is read from 16 consecutive memory locations and combined into a single 512-bit output.

### ALU (Arithmetic Logic Unit)

The ALU module performs the core arithmetic operations of the processor. It supports both multiplication and addition of 512-bit arrays. Based on a control signal, the ALU decides whether to perform addition or multiplication. The results of these operations are divided into a low part and a high part, which are stored in the registers A3 and A4, respectively. The multiplication result is split into a 512-bit lower part (A3) and a 512-bit higher part (A4). The addition result is stored directly in A3, with A4 being zero.

### Processor

The Processor module integrates the Register File, Memory, and ALU, controlling the data flow between these components. It manages the operations based on various control signals, ensuring that data is correctly transferred, processed, and stored. The processor also handles the loading of data from memory to registers and the storing of results back to memory, maintaining data integrity throughout the operations.

#### Operation Details

1. **Data Transfer**: The processor can load data from memory into the registers or store data from the registers into memory. This is controlled by a memory-to-register enable signal and a memory-to-register control signal.
2. **Arithmetic Operations**: The processor can perform addition or multiplication on the data in registers A1 and A2, storing the results in A3 and A4.
3. **Control Signals**: Various control signals determine the operation mode of the processor, such as whether to perform an arithmetic operation or a data transfer, and whether to load data from memory or store data to memory.

This structured approach ensures that the processor can handle complex arithmetic operations on large data sets efficiently and accurately. By simulating the design with tools like ModelSim, the functionality of the processor can be verified before implementing it on hardware such as an FPGA.

## How to Run

To run the application, use a Verilog simulator such as ModelSim or Icarus Verilog or an FPGA development board to implement the design. The testbench provided can be used to simulate the processor's behavior and verify its functionality.

1. Load the Verilog files into your simulation environment.
2. Compile it then Run the simulation and observe the output (or you can use VSCode extensions to run it As I did myself https://marketplace.visualstudio.com/items?itemName=itemName=leafvmaple.verilog).
3. For hardware implementation, synthesize the design and upload it to an FPGA.

## Results

After successfully running the simulation, the following outputs can be observed:

1. Data transfer between memory and registers.
2. Correct results from addition and multiplication operations.

## Related Links

- [Verilog](https://en.wikipedia.org/wiki/Verilog)
- [ModelSim](https://www.mentor.com/products/fv/modelsim/)
- [FPGA](https://en.wikipedia.org/wiki/Field-programmable_gate_array)

## Authors

- Mohammad Mahdi Abedian
