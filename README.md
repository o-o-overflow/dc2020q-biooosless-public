# BIOOOSLESS

- Players could write some shellcode that would run as part of the BIOS
- the goal: you need to read a file out of a floppy
- the twist: the BIOS stub does not have any standard BIOS routine
- the intended solution: players needed to figure out how to write a shellcode that implements its own floppy controller
- my intended solution, in practice: I stole some code from seabios, made it self-contained, and somehow extract the binary from the compiled ELF
