The stack is a fundamental data structure employed in computer programming for managing memory, operating on a Last-In, First-Out (LIFO) principle.

Imagine a physical stack of plates; the last plate placed on top is the first one removed. In the context of program execution, the stack is a contiguous memory region primarily dedicated to function calls. 

When a function is invoked, a specific area known as a stack frame is created. This frame acts as a workspace for that particular function call, housing its local variables, the arguments passed to it, and the critical return address, which dictates where execution should resume once the function completes its task.

The stack's dimensions are typically determined at compile time, and its automatic management is handled by both the compiler and the central processing unit (CPU), alleviating the programmer from manual allocation or deallocation tasks. 

Two pivotal CPU registers, the **stack pointer** (SP, often esp or rsp in x86 architectures) and the **base pointer** (BP, usually ebp or rbp), govern stack operations. 

The stack pointer consistently marks the topmost entry, while the base pointer serves as a stable reference to the base of the current stack frame, facilitating uncomplicated access to local variables and arguments. 

The stack expands downwards in memory; adding data through a "push" operation decreases the stack pointer, whereas removing data via a "pop" operation elevates it. However, this resource is finite, and careless usage, such as excessive recursion without a termination condition, can lead to a perilous stack overflow.