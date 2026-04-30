---
layout: page
title: "GDB"
permalink: /gdb
---
# Getting Started
1. Start the debugger with `gdb <executable>`
2. Configure layout and preferences
   -  `layout asm` will show the assembly
   -  `layout regs` will show the registers
   -  `layout src` will show the source code
   -  `layout split` will show 2 at the same time
   -  `set print object <on/off>` will specify the printing settings for objects (defaults to `off`)
     -  `on`: print derived/actual types
     -  `off`: print declared types for objects
4. Set your breakpoints
   - `break <funcName>` to set a breakpoint at the entry to the function `<funcName>`
   - `break *0x80483c3` to set a breakpoint at address `0x80483c3`
5. Run your program with `run`
6. Investigate at a breakpoint
  -  Print or examine memory
  -  `backtrace` to view the program stack
  -  `info frame` to describe the selected frame (use `info frame [addr]` to specify the frame at `addr`)
  -  `ptype [type]` to view a description of `type`, where `type` is a type, struct, etc
  -  `list` to show the next 1- lines of source code
  -  `disas` to show assembly of current function
7. Continue through the program
  - `step` will execute until the next line is reached
  - `stepi` will execute until the next instruction is reached
  - ` next` will execute the next line (including function calls, if applicable)
  - `finish` will run to the completino of the current function
  - ` continue` will execute until the next breakpoint (or end of program, if no remaining breakpoints)
  -  `until <location>` will execute until `location` is reached (useful for getting out of loops)
8. If things start looking garbled, use `refresh` to refresh the display
## Printing
A print command is of the form `print [/f] expr`, where `f` is the format specifier and `expr` is the expression to print the value of.
- Examples:
  - `print /d $rax`: print contents of %rax in decimal (/d)
## Examining Memory
To examine memory contents, use the form `x [/Nuf] expr` where `N` is the count of how many units to display, `u` is the unit size, `f` is the format specifier, and `expr` is the address of memory to examine.
- Examples:
  - `x /gx 0xbffff890`: examine 8 bytes (/g) in hex (/x) starting at address 0xbffff890
  - `x /s 0xbffff890`: examine string (/s) stored at 0xbffff890 (stops when it encounters '\0')
  - `x /i $rip`: examine instruction stored by $rip

# Reference
## Format Specifiers
|Format specifier|Format|Format specifier|Format|
|--|--|--|--|
|x|hexadecimal|a|address, absolute and relative|
|d|signed decimal|c|character|
|u|unsigned decimal|f|floating point|
|o|octal|i|instruction|
|t|binary|s|null-terminated string|
## Unit Sizes
|Specifier|Unit size|
|--|--|
|b|individual bytes|
|h|halfwords (two bytes)|
|w|words (four bytes)|
|g|giant words (eight bytes)|
