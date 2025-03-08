endbr64, security measure
push, saves on the stack the LP and BP to be able to trace back
mov, moves data from reg2 to reg1

to xor something with itself is a faster way to write 0 in a register than actuallluy writing 0

leave destructures part of the stack

eax return value register

objdump -x file: displays headers
objdump -d file: disassembles code
readelf -h file: reads ELF headers
readelf -s file: displays symbol table

strings elf: prints all printable strings from a file


