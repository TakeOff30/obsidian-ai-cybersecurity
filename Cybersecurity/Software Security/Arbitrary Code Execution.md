Can be induced by code injection or code reuse.
Return to libc attack
	exploit a buffer overflow to change the return value of a function to a pointer to a function from the standard library. First we find the start of the system libc function, find the address of a string /bin/sh and corrupt the stack to change the return pointer. We do not need an executable stack. To find these ingredients we can use gdb to find the addresses of the system function.
Return Oriented Programming
	the goal is to obtain in the stack a sequence of return pointers: these return pointers chain gadget of assembly code that can be used to execute anything.
	Gadgets are used for loading and storing data from register to register, register to memory and memory to register. For each parameter i want to load i need a POP instruction, then i chain functions by chaining their memory adresses
	
Jump Oriented Programming
	triggers the execution of a given function by exploiting the jump instructions instead of the ret instructions
	
