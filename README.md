





# SYSMON65

*SYSMON65* was developed for my 65C02 single board computer (SBC). My SBC contains the venerable 65C02 processor, a 6551 (ACIA), a 6522 (VIA), and the core chips found in most SBCs which typically include, a ROM (27C256) chip, a RAM chip, and address decoding logic chips. The 

This monitor may be ported to other 65C02 based SBCs with a few minor modifications. SYSMON65 includes and uses the 65C02 instructions (eg: phx,plx,bra etc) . However it could be converted back to a 6502 only instructions - if anyone was really interested - such as  KIM-1, Apple II series computers, the Commodore 64, the VIC-20, and more.

After searching the internet and reviewing the few 6502 operating systems and monitor software that I could find, I discovered that I only liked some of the functionality of each. Therefore, I decided to develop my own monitor software. During early development, the memory footprint of the monitor software was not considered, but as development progressed this became a priority, so I kept the code size “real tight”!

My goal for *SYSMON65* is to be a software development tool on an SBC. The user may paste code into the terminal, compile code, do memory dumps, decode, edit code, and much more…

Parts of my code was inspired by the following:

- The *A1 Assembler* by San Bergmans
   I like the front-end editor, but the assembler does not come with a dissembler. The assembler is a 2-pass assembler and feels very solid, but it was written primarily for an Apple computer. With San’s permission I used his front-end editor code, reviewed every line, and eventually re-wrote most of this. 


- The KRUSADER by Ken Wessen
   This has a super-efficient disassembler (most likely created by MOS and used by Apple) and includes the specific 65C02 instructions. With respect, I didn’t like the front-end editor.

The look and feel of *SYSMON65* were heavily influenced by the famous line-oriented debugger Debug https://en.wikipedia.org/wiki/Debug_(command) found in DOS (those were the days!). Some *Debug* front-end functionality can be found in *SYSMON65*, including the [Backspace] key to fix mistypes, and command history functionality with the [Up arrow] key.

*SYSMON65* is a full 2-pass assembler, with local and global labels, directives, and more. A 65C02 disassembler is included which includes Step-By-Step debugging (i.e., Tracing), memory dump, ASCII dump, fill, delete, block move, intel hex loader and more.

*SYSMON65* has been tested on a N65C02 hardware. It also includes code for an LCD 16x2 module. The software currently takes just over 3.2KB of memory space.