# Simplest Architecture Possible (SAP-1) – 8-Bit CPU in Logisim

## 1. What is SAP-1 Architecture?
The **SAP-1 (Simple-As-Possible 1)** is a basic computer architecture model introduced in the book *Digital Computer Electronics* by **Albert Paul Malvino**.

- It is a teaching model that is designed to help students understand the **fundamental concepts of computer organization and CPU design**.  
- SAP-1 is an **8-bit microprocessor architecture** with a very limited instruction set (5 OPCODES) and minimal hardware components.  
- It demonstrates the **core principles of how a CPU works**: The Fetch-Decode-Execute Cycle
- SAP-1 forms the **foundation** for more advanced models and later CPU designs.  

---

## 2. Why Build The SAP-1 CPU Architecture?

- **Conceptual Clarity** – It teaches how instructions are executed at the hardware level.  
- **Hands-On Learning** – Building SAP-1 shows how registers, memory, and control logic interact.  
- **Foundation for Growth** – Knowledge of SAP-1 makes it easier to understand real-world microprocessors (Intel 8085, ARM, RISC-V, etc.).  
- **Debugging & Optimization** – Programmers with hardware insights can write more efficient software.  

### By building SAP-1, you learn:
- How the **fetch-decode-execute cycle** works.  
- The role of **control signals** in orchestrating operations.  
- Basics of **binary instruction encoding**.  
- How a **minimal instruction set** can still perform useful computation.  

---

## 3. Components of SAP-1 (in detail)
The SAP-1 architecture contains a minimal set of components needed to demonstrate CPU functionality:

### Program Counter (PC)
- Holds the address of the next instruction to be executed.  
- Increments after each instruction fetch.  

### Instruction Register (IR)
- Stores the instruction currently being executed.  
- Splits into **opcode** (operation) and **operand** (data/memory address).  

### Memory Address Register (MAR)
- Holds the address of the memory location of the Operand being accessed.  

### Random Access Memory (RAM)
- 16 Bytes(or 8 * 16 bits) of Memory in SAP-1.  
- Stores both instructions and data.
- Data needs to be stored after all the instructions (after HALT).

### Accumulator (ACC)
- An 8-bit register used for arithmetic and logic operations.  

### B Register
- Temporary storage for operands used in arithmetic operations.  

### Output Register
- Displays the result of operations (simulates an output device).  

### Arithmetic Logic Unit (ALU)
- Performs basic arithmetic (addition or subtraction).

### Control Unit
- Driven by a clock.
- Generates timing and control signals.  
- Coordinates the **fetch-decode-execute cycle**.

---

## 4. Instruction Set of SAP-1
The SAP-1 instruction set is deliberately **small and simple**.  
Each instruction is **8 bits**:  
- The first 4 bits = **opcode** (operation).  
- The last 4 bits = **operand** (memory address or data).  

### 📝 SAP-1 Instruction Set

| Instruction | Binary Opcode | Hex  | Pseudo Assembly | Description |
|-------------|---------------|------|-----------------|-------------|
| **LDA addr** | 0001 AAAA    | 0x1A | `LDA 0xA`       | Load value from memory (address = AAAA) into Accumulator |
| **ADD addr** | 0010 AAAA    | 0x2A | `ADD 0xA`       | Add value from memory to Accumulator |
| **SUB addr** | 0011 AAAA    | 0x3A | `SUB 0xA`       | Subtract value from memory from Accumulator |
| **OUT**      | 0111 XXXX    | 0x7X | `OUT`           | Send Accumulator content to Output Register |
| **HLT**      | 1111 XXXX    | 0xFX | `HLT`           | Halt program execution |

---

## 5. Scope for Scalability
While SAP-1 is intentionally minimal, it can be extended step by step into a more capable CPU. Some possible enhancements include:

- **Expanded Instruction Set**  
  Add more opcodes such as `JMP`, `JZ` (Jump if Zero), `AND`, `OR`, `XOR`, etc.

- **Larger Memory**  
  Extend RAM from 16 bytes to 256 bytes or more, enabling more complex programs.  

- **Stack & Subroutines**  
  Introduce a stack pointer and CALL/RET instructions to support function calls and recursion.  

- **Improved ALU**  
  Add multiplication, division, bitwise logic, and shift/rotate operations.  

- **Input Devices**  
  Along with `OUT`, add an `IN` instruction to accept input from a simulated device or keyboard.  

- **Multiple Registers**  
  Introduce general-purpose registers (R0, R1, etc.) for faster computation and flexibility.  

- **Interrupt Handling**  
  Add basic interrupt support to demonstrate how CPUs handle external signals.  

- **Pipelining / Microprogramming**  
  Step toward modern CPU design concepts by experimenting with parallel execution and microcode control.  

These extensions transform SAP-1 into **SAP-2 and beyond**, bridging the gap between an educational toy CPU and the architecture of real-world processors.

---

This project replicates the **SAP-1 CPU in Logisim**, providing a hands-on way to visualize how each instruction moves through the CPU components.
