```
░██████╗██╗░░░██╗░██████╗███╗░░░███╗░█████╗░███╗░░██╗░█████╗░███████╗
██╔════╝╚██╗░██╔╝██╔════╝████╗░████║██╔══██╗████╗░██║██╔═══╝░██╔════╝
╚█████╗░░╚████╔╝░╚█████╗░██╔████╔██║██║░░██║██╔██╗██║██████╗░██████╗░
░╚═══██╗░░╚██╔╝░░░╚═══██╗██║╚██╔╝██║██║░░██║██║╚████║██╔══██╗╚════██╗
██████╔╝░░░██║░░░██████╔╝██║░╚═╝░██║╚█████╔╝██║░╚███║╚█████╔╝██████╔╝
╚═════╝░░░░╚═╝░░░╚═════╝░╚═╝░░░░░╚═╝░╚════╝░╚═╝░░╚══╝░╚════╝░╚═════╝░
```

# SYSMON65 (Version 2.30)

**SYSMON65** is my custom-built operating system designed for 65C02-based Single Board Computers (SBCs). 

My primary goal for SYSMON65 is to provide a complete, standalone software development tool directly on the SBC. 
You can paste code into the terminal, compile it, perform memory dumps, decode instructions, edit code, and much more—all natively. 

While heavily optimized utilizing specific 65C02 instructions (like `phx`, `plx`, `bra`, etc.), the core concepts can be ported back to standard 6502 instructions for use with classic hardware like the KIM-1, Apple II series, Commodore 64, or VIC-20.

---

##  Target Hardware & Environment

SYSMON65 was built for and tested on real hardware running an N65C02 processor. 
* **CPU:** WDC 65C02 Microprocessor.
* **UART:** 6551 ACIA for serial communications (Features a bug-free implementation that bypasses the infamous Xmit bug).
* **Terminal:** Designed for ANSI screen codes over Serial at **57600 baud (N81)**.
* **I/O:** 6522 VIA for input/output ports.
* **Memory:** 27C256 ROM and standard RAM chips.
* **Display:** Includes an integrated library to drive a 16x2 HD44780-compatible LCD Module.

---

## Core Features
The OS is highly optimized, currently taking just over **7.2KB** of memory space while packing in massive functionality:

* **Full 2-Pass Symbolic Assembler:** Supports local/global labels, integer math expressions (+, -, *, /), and directives (`.AS`, `.AT`, `.BS`, `.DA`, `.EQ`, `.OR`, `.TA`).
* **65C02 Disassembler:** Accurately decodes standard and CMOS-specific instructions.
* **Trace & Watch Debugger:** Step through code line-by-line while watching CPU flags, registers, the Program Counter, and custom memory addresses.
* **Memory Tools:** Inspect and modify memory limits, fill memory blocks, copy memory ranges, and perform Hex/ASCII dumps.
* **Intel Hex Loader:** Auto-detects the `:` character to automatically download pasted Intel Hex file contents. If configured, 4 LEDs on the VIA ports will flash ("Knight Rider" style) with every block read.
* **Built-in Calculator:** Use the Value (`V`) command to convert between Hex, Decimal, Binary, and ASCII, or evaluate mathematical expressions.
* **ROM Library & User Extensibility:** Access built-in ROM routines (like `WRCHAR` or `CLS`) or extend the OS commands via the `USERKEYDEF` vector.
* **Quality of Life UI:** Features `[Backspace]` support to fix mistypes, `[Up arrow]` command history, and Auto line-numbering (`A`) for the assembler.

---

##  Background & Inspirations
After searching the internet and reviewing the few 6502 operating systems and monitor software available, I discovered that I only liked scattered parts of each. 
I decided to develop my own OS from the ground up. 

The look and feel of SYSMON65 was heavily influenced by the famous line-oriented **DOS Debug** command. Initially, the memory footprint of the OS was not a concern, but as development progressed, optimizing and saving every single byte became a top priority.

Parts of my code were directly inspired by the following incredible projects:

* **The A1 Assembler by San Bergmans:** I loved the front-end editor, and the 2-pass assembler felt incredibly solid. Because it was written for the Apple II, it was limited to the standard 6502 instruction set and lacked a disassembler. With San’s permission, I used his front-end editor code only, reviewed every line, and ultimately as you do, rewrote most of it to fully integrate 65C02 instructions into my OS.

---
**Author:** Joe DiMeglio  
