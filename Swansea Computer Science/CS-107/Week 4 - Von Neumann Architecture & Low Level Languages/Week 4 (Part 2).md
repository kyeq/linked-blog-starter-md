#CS107 

## Introduction to low-level languages
- **One memory, both contents:** instructions and data are stored together. A machine is programmed by loading a program rather than rewiring it.
- **Five parts:** Input, output, memory, the arithmetic and logic unit, and the control unit.
- **The CPU:** the control unit and the ALU together, with registers holding the values in use.
- **Three buses connect them:** address, data and control

**The thing that connects everything together is called a bus.**

**The principle of abstraction**
The concept of hiding away the complicated details to allow us to focus on the key details we are interested in. This also applies in programming languages, with lower-level and higher-level languages.

### What's machine language?
A language made up of binary coded instructions built into the hardware of a particular computer and used directly by the computer.
*(8-bit machine code)*

#### Why would anyone choose to use machine language?
- To communicate with hardware directly. Fine-grain control.

Every processor type can have its own specific set of machine instructions.
The digital logic of the CPU recognises the binary representations of the instructions.

## Pep/9 Virtual computer
A virtual, hypothetical machine designed to contain the important features of a real computer that we want to illustrate (another word would be an abstract machine)

Pep/9: A virtual computer designed by Stanley Warford that has 40 machine-language instructions.

### Instruction format
- Operation code: specifies which instruction is to be carried out.
- Register specifier: Specifies which register is to be used (for our purposes it always specifies the accumulator 0)
- Addressing-mode: specifier Says how to interpret the operand part of the instruction

#### Addressing mode
Indicates whether value is stored in operand specifier or memory.

**Addressing modes: immediate**
![[Pasted image 20261023101714.png|403]]

**Addressing modes: direct**
![[Pasted image 20261023101748.png|414]]

#### What can you do in this language?

**Operation codes, important!**
![[Pasted image 20261023101820.png|369]]

#### Input and output in Pep/9
we can use **memory-mapped** I/O, where our input and output devices are connected to physical memory locations.

In Pep/9:
- Input device is at location FC15
- output device is at location FC16

**to get input in:**
load the value within FC15 to the accumulator

**to get output out:**
Load a value into the accumulator, and then store it to FC16

> Both of these only accept a single byte of information. No more!

### Example program 1
Let's print the classic "Hello World" string to the output device.

Steps required:
- Load the letter H into the accumulator.
- Store the value in the accumulator to the output device.
- Load the letter e into the accumulator.

![[Pasted image 20261023102759.png|490]]

...

![[Pasted image 20261023103312.png|492]]

You can express the code in hexadecimal chunks, though its hard to memorise.

![[Pasted image 20261023103331.png|493]]

There are particular ways to represent data as letters.

![[Pasted image 20261023103345.png|499]]

...

![[Pasted image 20261023103403.png]]