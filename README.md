





# SYSMON65

*SYSMON65* is a system monitor which has been developed for my custom built 65C02 single board computer (SBC). This monitor can easily be ported to other 65C02 based SBCs. SYSMON65 also supports 65C02 specific instructions, such as phx, plx, bra, and more. However, it may be converted back to 6502 specific instructions (if anyone were really interested in do so) for use with the KIM-1, Apple II series computers, Commodore 64, VIC-20, and other hardware implementations.

My SBC includes the venerable 65C02 processor, a 6551 for UART functionality, a 6522 chip for I/O ports, a 27C256 typical ROM and RAM chips, and address decoding logic chips.

After searching the internet and reviewing the few 6502 operating systems and monitor software that I could find, I discovered that I only liked parts of the functionality of each. So, I decided to develop my own monitor software. During early development, the memory footprint of the monitor software was not considered, but as development progressed this became a priority, I had to keep it “real tight”!

My goal for *SYSMON65* is to be a software development tool for my SBC. A user may paste code into the terminal, compile it, do memory dumps, decode it, edit the code, and much more…

Parts of my code was inspired by the following:

- The *A1 Assembler* by San Bergmans
   I like the front-end editor, but the assembler does not come with a dissembler. The assembler is a 2-pass assembler and feels very solid, but it was written primarily for an Apple computer. With San’s permission I used his front-end editor code, reviewed every line, and eventually re-wrote most of this. 

- The KRUSADER by Ken Wessen
   This has a super-efficient disassembler (most likely created by MOS and used by Apple) and includes the specific 65C02 instructions. With respect, I did not like the front-end editor.

The look and feel of *SYSMON65* was heavily influenced by the famous line-oriented debugger Debug https://en.wikipedia.org/wiki/Debug_(command) found in DOS (those were the days!). Some *Debug* front-end functionality can be found in *SYSMON65*, including the [Backspace] key to fix mistypes, and command history functionality using the [Up arrow] key.

*SYSMON65* includes a full 2-pass assembler with local and global labels, directives, and more. A 65C02 disassembler is included which includes step-by-step debugging (aka Tracing), memory dumps, ASCII dumps, fill, delete, block move, intel hex loader and more.

*SYSMON65* has been tested on hardware running a N65C02 processor. It also includes code for an LCD 16x2 module. The software currently takes just over 7.2KB of memory space.