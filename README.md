# RISC-V Processor Implementation

## Overview

This project implements a RISC-V processor in Verilog. The design includes the main components of a processor such as the ALU, control unit, instruction memory, data memory, and pipeline stages. This implementation is intended for educational purposes and can be used as a basis for further development and learning about processor design.

## Directory Structure

```
RISC_V_Implementation/
├── ALU.v
├── ALU_Decoder.v
├── Control_Unit_Top.v
├── Data_Memory.v
├── Decode_Cyle.v
├── dump.vcd
├── Execute_Cycle.v
├── Fetch_Cycle.v
├── Hazard_unit.v
├── Instruction_Memory.v
├── Main_Decoder.v
├── memfile.hex
├── Memory_Cycle.v
├── Mux.v
├── PC.v
├── PC_Adder.v
├── Pipeline_out.vvp
├── pipeline_tb.v
├── Pipeline_Top.v
├── Register_File.v
├── Sign_Extend.v
└── Writeback_Cycle.v
```

## Files Description

- `ALU.v`: Arithmetic Logic Unit, responsible for performing arithmetic and logical operations.
- `ALU_Decoder.v`: Decodes the ALU operations.
- `Control_Unit_Top.v`: Top-level control unit for managing the processor's control signals.
- `Data_Memory.v`: Data memory module for storing and retrieving data.
- `Decode_Cyle.v`: Handles the decode cycle of the pipeline.
- `dump.vcd`: Value Change Dump file for waveform analysis.
- `Execute_Cycle.v`: Manages the execute cycle of the pipeline.
- `Fetch_Cycle.v`: Handles the fetch cycle of the pipeline.
- `Hazard_unit.v`: Detects and handles hazards in the pipeline.
- `Instruction_Memory.v`: Instruction memory module for storing program instructions.
- `Main_Decoder.v`: Main decoder for the instruction set.
- `memfile.hex`: Memory initialization file.
- `Memory_Cycle.v`: Manages the memory cycle of the pipeline.
- `Mux.v`: Multiplexer module used in various parts of the design.
- `PC.v`: Program Counter module.
- `PC_Adder.v`: Program Counter Adder module.
- `Pipeline_out.vvp`: Output file from the simulation.
- `pipeline_tb.v`: Testbench for the pipeline implementation.
- `Pipeline_Top.v`: Top-level module for the pipeline.
- `Register_File.v`: Register file module for storing processor registers.
- `Sign_Extend.v`: Sign extension module for immediate values.
- `Writeback_Cycle.v`: Manages the writeback cycle of the pipeline.

## How to Run

1. **Set up your environment:**
   Ensure you have a Verilog simulator installed, such as Icarus Verilog.

2. **Compile the Verilog files:**
   ```bash
   iverilog -o Pipeline_out.vvp pipeline_tb.v
   ```

3. **Run the simulation:**
   ```bash
   vvp Pipeline_out.vvp
   ```

4. **View the waveform:**
   Use a waveform viewer such as GTKWave to open `dump.vcd`.

   ```bash
   gtkwave dump.vcd
   ```

## Project Details

### ALU

The ALU performs arithmetic and logical operations based on the control signals from the ALU decoder. It supports operations such as addition, subtraction, AND, OR, and XOR.

### Control Unit

The control unit generates the control signals required to manage the operation of the processor. It interfaces with the main decoder to decode instructions and produce appropriate control signals.

### Pipeline Stages

The processor is designed with a five-stage pipeline:
1. **Fetch Cycle**: Fetches instructions from the instruction memory.
2. **Decode Cycle**: Decodes instructions and reads register values.
3. **Execute Cycle**: Executes arithmetic and logical operations.
4. **Memory Cycle**: Accesses data memory for load/store instructions.
5. **Writeback Cycle**: Writes results back to the register file.
