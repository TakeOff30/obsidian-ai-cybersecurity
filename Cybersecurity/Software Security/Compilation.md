- The next phase is the compilation itself, undertaken by the compiler. The compiler's task is to translate the preprocessed C code into assembly language, an intermediary representation closer to machine code, but still human-readable. This [[Assembly]] code is then handed to the assembler which translates it into machine code, or binary instructions, specific to the target processor architecture (e.g., x86-64, ARM).
    
- The output of this stage is an **object file** (typically with a .o extension). While this object file contains machine code, it is not yet a complete executable. Specifically, the code is not yet linked with the code contained inside the libraries used.
    
- The machine code within the object file represents the translated functions and data from the C source, but it may contain unresolved references, namely unresolved symbols for calling routines that are external to the current C file.
    
- The C file is transformed into machine language, in a binary form.