# DSL Maths — A Custom Programming Language Built in C

A fully functional **Domain-Specific Language (DSL)** for mathematical computation, built completely from scratch in C. This project implements every stage of a real compiler pipeline — from raw source text all the way to bytecode execution on a custom virtual machine.

> No libraries. No shortcuts. Just pure C and computer science fundamentals.

---

## What is this?

Most people *use* programming languages. This project *builds* one.

DSL Maths is a custom scripting language that can evaluate mathematical expressions, store variables, call built-in math functions, and print results — all powered by a handwritten compiler and VM written in C.

**Write this:**
let x = 10;
print x;
print sin(30);
print pow(2, 5);

**Get this:**
10.000000
0.500000
32.000000

---

## Architecture — how it works

The project implements a complete compiler pipeline in 5 stages:
Source Code (.dsl file)
│
▼
[ Lexer ]          → Tokenizes raw text into tokens (numbers, keywords, operators)
│
▼
[ Parser ]         → Builds an Abstract Syntax Tree (AST) from the token stream
│
▼
[ AST Printer ]      → Visualizes the tree structure for debugging
│
▼
[ Compiler ]        → Walks the AST and emits bytecode instructions
│
▼
[ VM ]           → Executes the bytecode on a stack-based virtual machine

---

## Features

- **Variables** — declare and store values with `let`
- **Arithmetic** — `+`, `-`, `*`, `/` with correct operator precedence
- **Built-in math functions** — `sin()`, `cos()`, `tan()`, `sqrt()`, `pow()`
- **Print statement** — output any expression or variable
- **REPL mode** — interactive shell for live expression evaluation
- **File mode** — run `.dsl` script files directly
- **AST visualization** — prints the full syntax tree after execution for learning/debugging

---

## File structure
DSL_maths/
├── main.c           # Entry point — REPL and file runner
├── lexer.c/.h       # Tokenizer — breaks source into tokens
├── parser.c/.h      # Parser — builds the Abstract Syntax Tree
├── ast_printer.c/.h # AST visualizer — prints the syntax tree
├── compiler.c/.h    # Bytecode compiler — AST → bytecode instructions
├── vm.c/.h          # Virtual Machine — executes the bytecode
├── program.dsl      # Sample DSL program
└── commands         # Build commands reference

---

## How to build and run

**Requirements:** GCC and a C compiler (Linux / Windows with MinGW)

**Build:**
gcc main.c lexer.c parser.c compiler.c vm.c ast_printer.c -o dsl -lm

**Run a script file:**
./dsl program.dsl

**Run in interactive REPL mode:**
./dsl

Output:
Educational DSL Compiler + VM
dsl> let x = 10;
dsl> print x;
10.000000
dsl> print pow(2, 8);
256.000000
dsl> exit

---

## Sample program
let x = 10;
let y = x + 5;
print y;
print sin(90);
print cos(0);
print sqrt(144);
print pow(3, 4);

Output:
15.000000
1.000000
1.000000
12.000000
81.000000

---

## Supported syntax

| Feature | Syntax | Example |
|--------|--------|---------|
| Variable declaration | let name = expr; | let x = 42; |
| Print | print expr; | print x + 1; |
| Addition | a + b | print 2 + 3; |
| Subtraction | a - b | print 10 - 4; |
| Multiplication | a * b | print 3 * 7; |
| Division | a / b | print 10 / 2; |
| Sine (degrees) | sin(x) | print sin(30); |
| Cosine (degrees) | cos(x) | print cos(60); |
| Tangent (degrees) | tan(x) | print tan(45); |
| Square root | sqrt(x) | print sqrt(16); |
| Power | pow(base, exp) | print pow(2, 10); |

---

## Tech stack

![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![GCC](https://img.shields.io/badge/GCC-A42E2B?style=for-the-badge&logo=gnu&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

**Concepts applied:**
- Lexical analysis and tokenization
- Recursive descent parsing
- Abstract Syntax Tree (AST) construction
- Bytecode compilation
- Stack-based Virtual Machine design
- Symbol table management

---

## What I learned building this

- How real compilers like GCC and Clang work under the hood
- How a stack-based VM executes instructions (similar to the JVM and CPython)
- How operator precedence is encoded in a recursive descent parser
- Memory management and pointer structures in C

---

## Connect

Made by **Rohit Sharma** — B.Tech AI & Data Science student

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rohit-sharma-47467928a)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/HAZE-16)
