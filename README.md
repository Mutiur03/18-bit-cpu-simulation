# 🖥️ 18-bit CPU Architecture Simulation in Logisim

This is an 18-bit CPU architecture designed and implemented in **Logisim** as part of the **CSE 2114: Computer Architecture Laboratory** course (Semester 2-1) at **Khulna University of Engineering & Technology (KUET)**. The project features a custom-designed CPU with a datapath, control unit, and instruction set architecture (ISA) supporting arithmetic, logical, memory access, and control flow operations.

## 📌 Project Overview

This project simulates a simplified 18-bit CPU using Logisim, focusing on core architectural elements and the fetch-decode-execute cycle. The CPU includes an 18-bit Arithmetic Logic Unit (ALU), memory registers (MAR, MBR, PC, IR, Accumulator), a control unit, and a 5-bit addressable RAM (32 addressable units, total size: 32 × 18 bits). It supports fundamental operations like addition, subtraction, logical AND/OR, branching, and halting.

## 🧠 Instruction Set Architecture (ISA)

The CPU supports the following instructions:

| Opcode | Instruction | Description                                     |
| ------ | ----------- | ----------------------------------------------- |
| 0000   | AND         | Bitwise AND between Accumulator (AC) and memory |
| 0001   | ADD         | Add memory content to AC                        |
| 0010   | STO         | Store AC content to memory                      |
| 0011   | ISZ         | Increment memory; skip if zero                  |
| 0100   | BS          | Branch and save return address                  |
| 0101   | BUN         | Unconditional branch                            |
| 0110   | LDA         | Load memory content into AC                     |
| 0111   | HLT         | Halt execution                                  |
| 1000   | OR          | Bitwise OR between AC and memory                |
| 1001   | SUB         | Subtract memory content from AC                 |
| 1010   | INC         | Increment AC                                    |

### Instruction Format

- **Bits 0-4**: Memory address (5 bits, 32 addressable units).
- **Bits 12-15**: Opcode (4 bits, defining the instruction).
- **Bits 5-11, 16-17**: Reserved ("don't care" bits).

## ⚙️ Components

- **Program Counter (PC)**: Stores the address of the next instruction.
- **Instruction Register (IR)**: Holds the current instruction for decoding.
- **Memory Address Register (MAR)**: Points to the memory location being accessed.
- **Memory Buffer Register (MBR)**: Temporarily stores data to/from memory.
- **Accumulator (AC)**: Main register for ALU operations and intermediate results.
- **Arithmetic Logic Unit (ALU)**: Performs arithmetic (ADD, SUB) and logical (AND, OR) operations.
- **Control Unit**: Generates control signals based on opcodes.
- **Main Memory**: 18-bit RAM with 5-bit address width (32 addressable units).

## 🔄 Instruction Cycle

1. **Fetch**: PC sends the address to MAR; memory fetches the instruction into IR via MBR.
2. **Decode**: Control unit interprets the opcode and configures control signals.
3. **Execute**: ALU or control logic performs the operation (e.g., arithmetic, memory access, or branching).

## 🧾 How to Run

1. **Install Logisim**:
   - Download Logisim from [SourceForge](http://www.cburch.com/logisim/) or an official mirror.
   - Ensure Java Runtime Environment (JRE) is installed.
2. **Clone the Repository**:
   ```bash
   git clone https://github.com/Mutiur03/18-bit-cpu-simulation.git
   ```
3. **Open the Circuit**:
   - Launch Logisim and open the `.circ` file (e.g., `2207097.circ`) from the project folder.
4. **Run the Simulation**:
   - Enable simulation in Logisim (`Simulate > Simulation Enabled`).
   - Set the clock to automatic or manually trigger it to step through cycles.
   - Load instructions and data into the RAM module.
   - Observe register values (PC, IR, MAR, MBR, AC) and ALU outputs.
5. **Debugging**:
   - Use Logisim’s probe tool to inspect signal values.
   - Verify control signals and instruction sequencing.

## 📂 Project Structure

- `2207097.circ`: Main Logisim circuit file for the 18-bit CPU.
- `README.md`: This documentation file.
- `LICENSE`: MIT License file for the project.

## 🙏 Acknowledgments

- **Dr. M.M.A. Hashem** sir and **Md. Sakhawat Hossain** sir for their guidance.
- **Logisim** developers for providing an intuitive platform.
- **Khulna University of Engineering & Technology** for the academic support.

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
