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

