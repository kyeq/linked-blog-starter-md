#CS107 

### Assembly Languages
**An assembly language** is a language that uses mnemonic codes to represent machine-language instructions. 

**Assembler** is a program that reads each of the instructions in mnemonic form and translates it into the machine-language equivalent.

Given that instructions can differ between chipsets, it is important to have a method to take our (slightly) higher level programming languages and convert them into machine code. It is **the machine code** that will be executed – the higher languages are used to provide ease to the programmer in developing more complex behaviours.

Common assembly languages include:
- ARM
- x86

**The assembly process**

![[Pasted image 20261026141417.png|486]]

![[Pasted image 20261026141437.png|528]]

#### Pep/9 assembly instructions
- There are 39 assembly instructions in Pep/9
- There are also N "pseudo-ops" which act as instructions to te assembler, not as instructions for the CPU to execute.
- We only take a look at a few of these, so that you can appreciate the purpose of assembly languages, the function of the assembler, and the behaviour when executed.

**Here are some examples of the instructions:**

![[Pasted image 20261026141624.png|534]]

#### What do the 'I' and the 'd' stand for?
the 'i' and the 'd' are addressing modes.

![[Pasted image 20261026141729.png|425]]

### Example program 3: Printing "Hi"

![[Pasted image 20261026141842.png]]

The assembler takes the previous assembly code and translates it to machine code.
It can then also be loaded into memory to be executed.
This requires us to translate the mnemonics and their operands into hexadecimal, and to place this into memory addressing (beginning with address 0)

#### Naming memory locations
For example, if we wanted to name the address which contains the literal value 5
**five:** .WORD 0x0005

This reserves a word-size of memory and places the hexadecimal value 0x0005 within it. This location will then be named "five". We can then use this name elsewhere in our code to refer to this memory address.

*Note: in this example, the address contains data, or a value*

For example, if we wanted to name the address which adds 5 to the accumulator:
**addfive:** ADDA 0x0005, i

This will name the memory address where the instruction is placed "addfive".
We can then use this name elsewhere in our code to refer to this memory address.

*Note:* in this example, the address contains an instruction.

### Branching and loops

- Remember the Fetch Decode Execute cycle?
- If we have a branching behaviour in our program, what is actually happening here is our program counter is updated to point to a new memory address, rather than the next sequential address.

In Pep/9 assembly, we can do this using instructions such as BR (branch always) BREQ (branch A == 0), BRGT (branch if A > 0). The operand for these instructions is the memory address to go to, if the condition is true.


