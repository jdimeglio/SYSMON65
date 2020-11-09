# 6502-Monitor

This is a 65C02 monitor developed for my 65C02 board. It contains a 65C02, 6551, 6522 and the usual ROM, RAM decoding etc. 

It can be ported onto any 65C02 based computer with some minor modifications. 
After searching the net i didnt like the many if not all the 6502 OS/Monitors. In my opinion i liked bits of them. So i decided to create my own.
I didnt care too much about space, more functionality. My goals was it to be a development machine. 

Able to paste code to the terminal, complile, it dump, decode it, edit it etc. 

Some of this code had been inspired by many before me - the A1 Assembler by San Bergmans https://www.sbprojects.net/whoami/index.php. 
I liked the Assembler but didnt come with a dissembler. Its 2 pass assembler and felt solid - but mostly written for an Apple.  
With his permission i used his front end, but for effecicienty removed all the back end compiling code. 

On the othe hand The KRUSADER by Ken Wessen had the supper effecient dissambler that ive seen before (probably created by MOS and used by Apple) and i was tackling the addition of 65C02 instructions. 

I have to say i first wrote a monitor/OS back in 1992 on a 65C02 computer we built as part of my electronics engineering course. It had "everything" but an assembler. 
Thought i'd add the ellusive assembler. In researching i learnt better ways to dissembler code - so not using all my code however ive perfer my interface. 
Also the old DOS debug command is how i want the console to feel like. I already had that in my 1992 and im not setting backwards on this point - in otherwords, mistyping something means hitting the backspace not having to retyping the whole line again as many of these monitors have you do. 

