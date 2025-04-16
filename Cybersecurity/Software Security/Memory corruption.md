Buffer overflow
	happen with arrays, pointer, strings
	can be exploited to change values of variables in the stack
	we can change the return address of a function
		we can objdump to understand:
		- where is the function to execute
		- the length of the stack frame
		- where buffer is allocated and which bytes are used for the return address
	this allows to execute a function modifing the buffer and then will cause a segmentation fault because we set only the return value and not the entire stack frame
Code injection
	shellcode injection: write in the stack executable code to run a shell
		- often to detect buffer overflows cyclic strings are used this way we understand which byte broke the program and understand where the stack starts
		- we leverage gadgets
	printf is a vulnerable function for how it is structured: tokens passed which specify how the arguments are printed. Look at %s %x %nx %n$x and most of all %n
	
Canary are solutions that prevent pawning, attention when using forks
Address Space Layout Randomization
