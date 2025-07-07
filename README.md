# # 16-bit RISC Pipelined Processor using Verilog HDL

This project implements a custom 16-bit RISC Pipelined Processor using Verilog HDL. It features a compact **Reduced Instruction Set Architecture (RISA)** and a multi-stage pipelined datapath that executes approximately **one instruction per clock cycle**, improving instruction throughput significantly.

---

**Features**

- **Harvard Architecture**: Separate instruction and data memory access.
- **Custom RISA (Reduced Instruction Set Architecture)** with essential instructions.
- **Pipelined Design**: Multi-stage pipeline (Fetch, Decode, Execute, Write Back).
- **32 General-Purpose Registers** (16-bit each).
- **256-Byte Data Memory** with Load/Store functionality.
- **Custom ALU** supporting arithmetic, logical, shift, rotate, and branch operations.
- **Program Counter & Stack Pointer** support for jumps, calls, and returns.
- **Instruction Throughput**: ~1 instruction per clock cycle.
- **Complete simulation and validation in Xilinx Vivado**.

---

**RTL Modules**

- `ALU.v` - Arithmetic Logic Unit
- `adder_16bit.v` - 16-bit Adder
- `Control_unit.v` - Control Signal Generator
- `Register_file.v` - 32×16 Register File
- `stack_pointer.v` - Stack Pointer
- `program_counter.v` - Program Counter
- `decoder_5x32.v`, `decoder_3x8.v` - Instruction Decoders
- `register_16bit.v`, `buffers.v`, `full_adder.v`, etc.

---

**Instruction Set Architecture (ISA)**

- Load/Store: `LD`, `STR`
- Arithmetic: `ADD`, `SUB`, `INR`, `DCR`, `ADC`, `SBB`, etc.
- Logical: `AND`, `OR`, `NOT`
- Shift & Rotate: `RCL`, `RCR`, `SIL`, `SOR`
- Branching: `JZ`, `JNZ`, `CZ`, `CNZ`, `RETZ`, `RETNZ`
- Stack: `LDSP`, `CALL`, `RET`
- Special: `HLT`, `NOP`

 *See `ISA 0`, `ISA 1` images for instruction formats.*



**Pipelining**

The processor is divided into the following pipeline stages:
1. **Instruction Fetch (IF)**
2. **Instruction Decode (ID)**
3. **Execute (EX)**
4. **Write Back (WB)**

This design enables efficient execution of instructions in parallel, with proper hazard management and NOP insertion where required.

---

**Simulation**

- Implemented and simulated all modules using **Xilinx Vivado**.
- Validated instruction flow, pipelining, control signals, and register file behavior.
- Verified performance improvements due to pipelined execution.

---

**Schematics**

- **Processor Block Diagram**: `processor_schematic1`, `processor_schematic2`
- **ALU Diagram**: `ALU_schematic`
- **Control Unit**: `Control_unit1_schematic`, `Control_unit2_schematic`
- **ISA Formats**: `ISA 0`, `ISA 1`

---

**Repository Structure**


Processor schematic
![processor_schematic1]
![processor_schematic2]

ALU schematic
![ALU_schematic]
Control unit schematic
![Control_unit1_schematic]
![Control_unit2_schematic]

ISA
![ISA 0]
![ISA 1]



**THANK YOU**