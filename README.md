RISC-V Single-Cycle and Pipelined Processor Design

This repository showcases the design and implementation of a 3-stage pipelined processor built on the RISC-V Instruction Set Architecture (ISA).

Overview of Supported Instructions

Data Processing Instructions

R-type: ADD, SUB, SLL, SLT, SLTU, XOR, SRL, SRA, OR, AND

I-type: ADDI, SLTI, SLTIU, XORI, ORI, ANDI, SLLI, SRLI, SRAI

U-type: LUI, AUIPC

Memory Access Instructions

I-type: LB, LH, LW, LBU, LHU

S-type: SB, SH, SW

Flow Control Instructions

J-type: JAL

I-type: JALR

B-type: BEQ, BNE, BLT, BGE, BLTU, BGEU

CSR Instructions

CSRRW, MRET

Interrupt Management

The processor is designed to handle timer interrupts effectively:

Interrupt Registration: Timer interrupts are captured in the mip register.

Saving PC: The current Program Counter (PC) is stored in the mepc register upon an interrupt.

ISR Execution: An interrupt service routine (ISR) provided by the user is executed.

Resumption: After completing the ISR, the mret instruction restores the PC from mepc and resumes execution.

Testing the Processor

The processor’s functionality has been validated through:

Greatest Common Divisor (GCD) program

Factorial calculation program

Details for the factorial example can be found in inst.mem. The GCD example is linked to a specific commit in this repository.

Compilation and Simulation

Compilation Instructions

Use the compile.bat script provided in this repository.

Alternatively, you can compile using the following commands:

For specific files:

vlog file1.sv file2.sv ...

For all SystemVerilog files in the directory:

vlog *.sv

A work directory will be generated to store compilation outputs.

Simulation Steps

Run the following command to simulate the design:

vsim -c top_level_module_name -do "run -all"

This generates a .vcd file containing the simulation results.

Viewing Simulation Results

To visualize the waveforms, use:

gtkwave dumpfile_name.vcd

By default, the dump file is named processor.vcd. You can analyze the signals and verify processor behavior using the GTKWave tool.

Conclusion

This project demonstrates a robust and efficient implementation of a RISC-V-based pipelined processor. The design handles hazards, interrupts, and control flow effectively, making it a great starting point for exploring RISC-V processor architectures.
