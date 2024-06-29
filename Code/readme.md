# Project Title: Design of a 512-bit Array Processor for Integer Arithmetic

## Code

### Register File

The Register File module is responsible for storing and retrieving four 512-bit arrays, named A1 to A4. These registers are updated on the positive edge of the clock signal. The Register File is implemented as an array of four 512-bit registers. Each register can be accessed and updated based on the clock signal. The Register File allows efficient storage and retrieval of large data arrays necessary for the processor's operations.

### Memory

The Memory module is designed with a depth of 512 and a width of 32 bits, simulating a memory structure that can load and store 16 consecutive memory locations in one operation. The Memory module allows data transfer between the memory and the registers. It supports writing data to memory and reading data from memory, using an address input and a write enable signal. During a write operation, the data input is divided into 32-bit chunks and written to 16 consecutive memory locations. During a read operation, data is read from 16 consecutive memory locations and combined into a single 512-bit output.

### ALU (Arithmetic Logic Unit)

The ALU module performs the core arithmetic operations of the processor. It supports both multiplication and addition of 512-bit arrays. Based on a control signal, the ALU decides whether to perform addition or multiplication. The results of these operations are divided into a low part and a high part, which are stored in the registers A3 and A4, respectively. The multiplication result is split into a 512-bit lower part (A3) and a 512-bit higher part (A4). The addition result is stored directly in A3, with A4 being zero.

### Processor

The Processor module integrates the Register File, Memory, and ALU, controlling the data flow between these components. It manages the operations based on various control signals, ensuring that data is correctly transferred, processed, and stored. The processor also handles the loading of data from memory to registers and the storing of results back to memory, maintaining data integrity throughout the operations.

### Testbench

The Testbench module is used to simulate the behavior of the processor. It includes clock generation and test sequences to verify the functionality of the Register File, Memory, and ALU. The testbench performs various operations such as data transfer between memory and registers, addition and multiplication operations, and verification of results.
