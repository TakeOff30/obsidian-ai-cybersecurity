Slow Printer
The program to reverse engineer prints a char of the flag waiting exponentially to print each char. It is not possible to decompile the program, the way to solve it is to use gdb debugger. 

After using strace we can find out which are the system calls done by the program and we find out that clock_nanosleep gets called. 

On gdb we can catch the system calls to clock_nanosleep and write the following command to set the value of the $rdx argument to 0 to prevent from waiting.

gdb ./slow_printer
catch syscall clock_nanosleep

commands
sleep
set $rdx = 0
continue
end

run