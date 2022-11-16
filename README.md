

░██████╗██╗░░░██╗░██████╗███╗░░░███╗░█████╗░███╗░░██╗░█████╗░███████╗
██╔════╝╚██╗░██╔╝██╔════╝████╗░████║██╔══██╗████╗░██║██╔═══╝░██╔════╝
╚█████╗░░╚████╔╝░╚█████╗░██╔████╔██║██║░░██║██╔██╗██║██████╗░██████╗░
░╚═══██╗░░╚██╔╝░░░╚═══██╗██║╚██╔╝██║██║░░██║██║╚████║██╔══██╗╚════██╗
██████╔╝░░░██║░░░██████╔╝██║░╚═╝░██║╚█████╔╝██║░╚███║╚█████╔╝██████╔╝
╚═════╝░░░░╚═╝░░░╚═════╝░╚═╝░░░░░╚═╝░╚════╝░╚═╝░░╚══╝░╚════╝░╚═════╝░


# SYSMON65

*SYSMON65* is an operating system for my custom built 65C02 single board computer (SBC). This OS can easily be ported to other 65C02 based SBCs. 
SYSMON65 uses the 65C02 specific instructions, such as phx, plx, bra, and more. However, it can be converted back to 6502 only instructions (if anyone were really interested in do so) for use with say the KIM-1, Apple II series computers, Commodore 64, VIC-20, and other hardware implementations.
My personal SBC includes the venerable 65C02 processor, a 6551 for UART functionality, a 6522 chip for I/O ports, a 27C256 typical ROM and RAM chips, LCD and address decoding logic chips.

After searching the internet and reviewing the few 6502 operating systems and monitor software that I could find, I discovered that I only liked parts of the functionality of each. 

So, I decided to develop my own OS – admittedly I had written one in 1990’s and it was inspired back when Windows had DEBUG. Initially the memory footprint of the OS was not considered, but as development progressed this became a priority - so where I can I save every byte I could.
My goal for *SYSMON65* is to be a software development tool for my SBC. A user may paste code into the terminal, compile it, do memory dumps, decode it, edit the code, and much more…

Parts of my code was inspired by the following:

- The *A1 Assembler* by San Bergmans
I liked the front-end editor only, but the assembler does not come with a dissembler. However the assembler is a 2-pass assembler and feels very solid, but it was written primarily for an Apple computer, and therefore limited to only 6502 instruction set.
With San’s permission I used his front-end editor code, reviewed every line, but eventually re-wrote most of it.  This allowed me to ensure I could get the full use of the 65C02 instructions but fully integrated it into my OS

- The KRUSADER by Ken Wessen
Among other things this has a super-efficient disassembler (most likely created by MOS and used by Apple) and includes the specific 65C02 instructions. With respect, I did not like anything else.

The look and feel of *SYSMON65* was heavily influenced by the famous line-oriented debugger Debug https://en.wikipedia.org/wiki/Debug_(command) found in DOS (those were the days!). Some *Debug* front-end functionality can be found in *SYSMON65*, including the [Backspace] key to fix mistypes, and command history functionality using the [Up arrow] key.

*SYSMON65* has a full 2-pass assembler with local and global labels, directives, and much more. A 65C02 disassembler is included. Ive also built step-by-step debugger (aka Tracing), memory dumps, ASCII dumps, fill, delete, block move, intel hex loader, Kermit and a library to drive LCD display to name a few.

*SYSMON65* has been tested on real hardware running a N65C02 processor. It also includes code for an LCD 16x2 module. The software currently takes just over 7.2KB of memory space.

