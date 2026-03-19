# Two-Pass Assembler System in C

A complete implementation of a two-pass assembler system in C, including parsing, symbol table generation, instruction encoding, and memory loading simulation.

---

## 👥 Contributors

This project was developed as a group project for the **CSE 232 - Systems Programming** course.

| Name | GitHub | Responsibility |
|------|--------|----------------|
| Yiğit Can Turan | [@Yigit1708](https://github.com/Yigit1708) | Assembler Pass 1, tables, and partial code implementation |
| Nisa Of | [@Nisaof](https://github.com/Nisaof) | Assembler Pass 1 and parser |
| Efe Demirci | [@efedemirci04](https://github.com/efedemirci04) | Assembler Pass 2 |
| Deniz Baltaş | [@denizbaltas](https://github.com/denizbaltas) | Linker |
| Işıl Hocaoğlu | - | Loader, integration, and Makefile |

---

## 💡 My Contribution

My main contributions to this project include:

- Implemented **symbol table** and **instruction table structures**
- Contributed to **Assembler Pass 1 logic** and parsing workflow
- Supported **partial object code generation**
- Participated in **system integration and debugging**

---

## 🧠 System Overview

The system follows a classic two-pass assembler pipeline:

```
.asm → Pass 1 → Pass 2 → Loader → Memory Execution
```

- **Pass 1:** Parses assembly code and builds the symbol table  
- **Pass 2:** Translates instructions into machine code  
- **Loader:** Loads executable into memory with relocation  
- **Execution:** Simulated memory output  

---

## 🛠️ Instruction Set (SMPL)

The assembler supports a custom instruction set including arithmetic, control flow, and memory operations.

| Mnemonic | Opcode | Mode | Description |
|----------|--------|------|-------------|
| ADD | A1/A2 | direct/immediate | AC ← AC + value |
| SUB | A3/A4 | direct/immediate | AC ← AC - value |
| LDA | E1/E2 | direct/immediate | Load to AC |
| STA | F1 | direct | Store AC to memory |
| BEQ | B1 | relative | Branch if AC = 0 |
| JMP | B4 | direct | Unconditional jump |
| CLL | C1 | direct | Call subroutine |
| RET | C2 | implied | Return |
| HLT | FE | implied | Halt execution |

> Full instruction set implementation can be found in `tables.c`

---

## ⚙️ Build & Run

### Requirements
- GCC  
- Linux (tested on Ubuntu)  

### Build
```bash
make
```

### Run
```bash
# Run full pipeline
./main test_main.asm

# Run loader separately
./loader_main program.exe program.t
```

---

## 📁 Project Structure

```bash
├── main.c           # Entry point
├── parser.c/.h      # Assembly parsing
├── tables.c/.h      # Symbol & opcode tables
├── pass1.c/.h       # Pass 1 (symbol table)
├── pass2.c/.h       # Pass 2 (machine code)
├── linker_exec.c    # Linker
├── loader.c/.h      # Loader
├── loader_main.c    # Loader entry
├── Makefile         # Build configuration
├── *.asm            # Sample assembly programs
```

---

## 🧪 Example

Sample `.asm` files are provided in the repository for testing and demonstration purposes.

---

## 👨‍💻 Author

Yiğit Can Turan  
Computer Engineering Student
