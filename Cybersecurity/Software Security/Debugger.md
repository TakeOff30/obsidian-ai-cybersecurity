A debugger is a software tool that allows a programmer to step through the execution of a program, examine the program's state (memory, registers, variables), and control its behavior. It provides a controlled environment for observing how a program runs, helping developers identify and fix errors (bugs) in their code. Debuggers are essential for both software development and security analysis.

 Debuggers facilitate dynamic analysis, where the program is executed and its behavior is observed in real-time. **Dynamic analysis** reveals how a program behaves under different conditions, including those that might trigger vulnerabilities.
- **GDB (GNU Debugger):** A powerful command-line debugger widely used on Linux and other Unix-like systems.
- **pwndbg:** An enhanced GDB plugin that adds many features to make debugging easier, especially for exploit development and reverse engineering. It includes features like:
    - Improved disassembly output
    - Heap visualization
    - Stack analysis
    - ROP gadget searching

**Ghidra:** A free and open-source reverse engineering framework for **static analysis** developed by the National Security Agency (NSA). Ghidra provides powerful tools for static analysis, including:
- Disassembler: Converts machine code into assembly language.
- Decompiler: Attempts to convert machine code into a higher-level language (like C).
- Symbol Analyzer: Identifies functions, variables, and data structures.

