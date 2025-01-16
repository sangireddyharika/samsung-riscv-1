RISC-V Mission 2025 | Driving Semiconductor Innovation 
Welcome to my GitHub repository! This space highlights my journey as part of RISC-V Mission 2025, an initiative by Samsung Semiconductor India Research (SSIR) and VLSI System Design (VSD).

About the Mission
RISC-V Mission 2025 aims to:

Build a skilled workforce of 1,000 RISC-V engineers in Karnataka.
Train engineering students with hands-on expertise in RISC-V and semiconductor technologies.
Strengthen India’s role in the global semiconductor ecosystem.
My Journey
Program Highlights
6-Week Training: Practical skills in RISC-V architecture and semiconductor technology.
RISC-V Development Board: Exclusive access to VSD-provided boards.
Remote Workshops: Hands-on training for Tier-2 and Tier-3 VTU colleges.
Online Learning: Intensive courses to reinforce skills.
🎓 Key Learnings
RISC-V Architecture: Core concepts, instruction sets, and applications.
Hardware-Software Co-Design: Seamless integration of software and RISC-V hardware.
VLSI Design: Techniques shaping the future of semiconductors.
Hands-On Projects: Real-world applications with RISC-V boards and tools.
Repository Highlights
Code Samples: Projects and implementations from the program.
Documentation: Insights, concepts, and assignments.
Project Showcase: A comprehensive project leveraging RISC-V and VLSI skills.
Vision
Through this initiative, I aim to:

Contribute to India’s semiconductor growth.
Deepen expertise in RISC-V and VLSI technologies.
Join the next generation of semiconductor innovators.
Let’s Collaborate!
Explore this repository, share your thoughts, or collaborate on exciting RISC-V projects. Together, let’s drive the future of semiconductor technology!

Acknowledgments
Grateful to:

Samsung Semiconductor India Research (SSIR)
VLSI System Design (VSD)
The entire RISC-V Mission 2025 team for this transformative experience.
Task 3
Instruction 1:
Machine code lui a2,0x376
![Screenshot_from_2025-01-15_20-49-11 1](https://github.com/user-attachments/assets/b4c49ab3-6f45-417e-a2c5-c5cd8713adc8)
Instruction: lui a2, 0x376

Address: 100b0

Machine Code: 00376637

Operation

Mnemonic: lui

Purpose: Load the immediate value 0x376 into the upper 20 bits of register a2 (x12). The lower 12 bits are set to 0.

Result in a2:

a2 = 0x37600000

Instruction Format (U-type for lui):

U-type format is:

[imm[31:12]] [rd] [opcode]

Immediate (imm[31:12]): A 20-bit value that is left-shifted by 12 to form the final 32-bit immediate value.

Destination Register (rd): Specifies where the result is stored.

Opcode: Specifies the operation (lui).

Immediate (imm[31:12]):

Immediate value 0x376 is converted to binary:

0x376 → 0011 0111 0110

This is placed in the top 20 bits.

Destination Register (rd):

Register a2 corresponds to x12 in RISC-V architecture.

x12 in binary:01100

Opcode:

Opcode for lui is 0110111 (7 bits).

Binary Representation

Combining the fields into binary:

[imm[31:12]]      [rd]    [opcode]  

0011 0111 0110    01100   0110111

Complete binary instruction:

0011 0111 0110 01100 0110111

Hexadecimal Representation

Convert the binary representation into hexadecimal:

0011 0111 0110 01100 0110111 → 0x00376637

Instruction 2

![Screenshot_from_2025-01-15_20-49-24 1](https://github.com/user-attachments/assets/24607619-db3d-41e3-b0a7-5f60ac95f21a)

Instruction: addi sp, sp, -16

Mnemonic: addi (Add Immediate)

Operation: Add an immediate value to a source register (sp) and store the result in the 

destination register (sp).

Machine Code: ff010113

Binary Representation:1111 1111 0000 0001 0000 0001 0001 0011

RISC-V addi uses the I-Type format:

Field	Bits	Value	Description

Immediate	[31:20]	1111 1111 0000	Immediate value (-16 in two's complement)

rs1	[19:15]	00010 (sp = x2)	Source register

funct3	[14:12]	000	Function code for addi

rd	[11:7]	00010 (sp = x2)	Destination register

Opcode	[6:0]	0010011	Opcode for addi

Immediate (bits [31:20])

Binary: 1111 1111 0000

This is a 12-bit signed value in two's complement.

Two's complement decoding:

Invert bits: 0000 0000 1111

Add 1: 0000 0001 0000 = 16

Since the most significant bit is 1, the value is negative: -16

Source Register (rs1, bits [19:15])

Binary: 00010

This maps to sp (x2).

Function Code (funct3, bits [14:12])

Binary: 000

Specifies the operation as addi (Add Immediate).

Destination Register (rd, bits [11:7])

Binary: 00010

This maps to sp (x2).

Opcode (bits [6:0])

Binary: 0010011

This is the opcode for addi.

Instruction 3

![Screenshot_from_2025-01-15_20-49-33 1](https://github.com/user-attachments/assets/dfec7ac0-d6cf-4d61-ad1a-41285d6af698)

Explanation
Opcode (0010011):

Identifies this as an addi (add immediate) instruction.
Immediate (-256):

Represented as a 12-bit signed number: 1111 0000 0000.
The two's complement interpretation of 1111 0000 0000 gives -256.
rs1 (00101):

Specifies the source register a2 (x5).
funct3 (000):

Function code for addition.
rd (00101):

Specifies the destination register a2 (x5).

This instruction subtracts 256 from the value in register a2 (x5) and stores the result back into a2. If a2 initially contained 0x37600000, after this instruction, it will contain 0x375F0000.

Instruction 4 

![Screenshot_from_2025-01-15_20-49-42 1](https://github.com/user-attachments/assets/59ec004a-7689-46a5-aad9-3312044a48d2)
The li (load immediate) pseudo-instruction is represented as a combination of actual instructions. In this case, li a1, 10 is implemented directly using the addi instruction with the source register x0 (zero register). Here's the breakdown:

Explanation
Opcode (0010011):

Identifies this as an addi (add immediate) instruction.
Immediate (10):

Represented as a 12-bit unsigned value: 0000 0000 1010.
rs1 (00000):

Source register is x0 (zero register), which always holds the value 0.
funct3 (000):

Specifies addition operation for addi.
rd (00101):

Specifies the destination register a1 (x11).

Operation
The addi instruction performs the following:
a1 = x0 + 10
Since x0 always contains 0, the result is simply 10. The value 10 is then stored in a1.

The instruction li a1, 10 is encoded as addi a1, x0, 10, loading the immediate value 10 into the a1 register.

Instruction 5

![Screenshot_from_2025-01-15_20-49-48 1](https://github.com/user-attachments/assets/23ad2f31-5e13-403d-83ef-0a61d82738e0)

Explanation
Opcode (0010011):

Identifies this as an addi (add immediate) instruction.
Immediate (464):

Represented as a 12-bit unsigned value: 0001 1101 0000.
rs1 (00101):

Source register is a0 (x10).
funct3 (000):

Specifies addition operation for addi.
rd (00101):

Specifies the destination register a0 (x10).

Operation
The addi instruction performs the following:

a0 = a0 + 464
If a0 initially contained 0x21000000, the result after adding 464 (0x1D0) is:

a0 = 0x210001D0

The instruction addi a0, a0, 464 adds the immediate value 464 (0x1D0) to the current value of a0, and stores the result back into a0. After this instruction, a0 contains the value 0x210001D0.

Instruction 6 

![Screenshot_from_2025-01-15_20-49-56 1](https://github.com/user-attachments/assets/fb0212fe-3a27-4c3a-80ba-784e407500b3)

This instruction uses the sd (store double) operation to store the value in the ra register into memory at an offset of 8 from the address in the sp register. Here’s the detailed breakdown:

Explanation
Opcode (0100011):

Identifies this as a store instruction (sd).
Immediate (8):

12-bit immediate value split into two parts:
High 7 bits (0000000) go to bits [31:25].
Low 5 bits (01000) go to bits [11:7].
rs1 (00010):

Specifies the base address register as sp (x2).
rs2 (00001):

Specifies the source register as ra (x1).
funct3 (011):

Specifies the operation as sd (store double).
Operation
The sd instruction performs the following:

MEM[sp + 8] = ra
It calculates the memory address by adding the offset 8 to the value in sp.
The value in the ra register is stored in the calculated memory address.

The instruction sd ra, 8(sp) stores the value in the ra register (x1) into memory at an offset of 8 bytes from the address in the sp register (x2). This is typically used to save the return address on the stack before making a function call.

Instruction 7

![Screenshot_from_2025-01-15_20-50-03 1](https://github.com/user-attachments/assets/2d1c8af6-bc99-42f1-bd7a-5585d01822f4)

The jal (jump and link) instruction performs a jump to a target address and stores the return address (address of the next instruction) in the ra (x1) register. Here’s the detailed breakdown:

Explanation
Opcode (1101111):

Identifies this as a jal (jump and link) instruction.
Immediate (10484):

The jump offset is encoded as a 20-bit signed immediate value:
Bits [20]: 0 (sign-extended for positive offset).
Bits [10:1]: 1111011100 (low 10 bits of offset).
Bits [19:12]: 00111000 (high 8 bits of offset).
The offset is added to the program counter (PC) to compute the target address.
rd (00001):

Specifies the destination register for the return address as ra (x1).

Operation
The jal instruction performs two actions:

Calculates the target address by adding the offset 10484 to the current PC (program counter).
Stores the return address (PC + 4, the address of the next instruction) into the ra register.

The instruction jal ra, 10484 <printf> makes an unconditional jump to the address 10484 (relative to the current PC) and stores the return address in the ra register. This is typically used for function calls, and in this case, it jumps to the printf function located at address 10484.

Instruction 8

![Screenshot_from_2025-01-15_20-50-12 1](https://github.com/user-attachments/assets/6db42a59-d577-44e3-abdc-8d6eb83cf62a)

Breakdown of Instruction:
The ld (load double) instruction loads a 64-bit value from memory into a register. Here’s the detailed breakdown:

Explanation
Opcode (0000011):

Identifies this as a load instruction (ld).
Immediate (8):

Represents the memory offset (8 bytes) as a 12-bit signed value.
rs1 (00010):

Specifies the base address register as sp (x2).
funct3 (011):

Specifies the operation as ld (load double).
rd (00001):

Specifies the destination register as ra (x1).
Operation
The ld instruction performs the following:

ra = MEM[sp + 8]
It calculates the memory address by adding the offset 8 to the value in the sp register.
The 64-bit value stored at this memory location is loaded into the ra register.

The instruction ld ra, 8(sp) loads the 64-bit value from the memory address calculated as sp + 8 into the ra (x1) register. This is commonly used to restore the return address from the stack after a function call.

Instruction 9 

![Screenshot_from_2025-01-15_20-50-19 1](https://github.com/user-attachments/assets/14f3cc91-33a2-41e7-9bd3-e559fdf855fb)

The li (load immediate) is a pseudoinstruction in RISC-V that gets translated into a base instruction, typically addi. Here, li a0, 0 is equivalent to:

addi a0, x0, 0

Explanation
Opcode (0010011):

Identifies this as an addi (add immediate) instruction.
Immediate (0):

12-bit signed immediate value to be added.
rs1 (00000):

Source register is x0, which always holds the value 0.
funct3 (000):

Specifies addition operation for addi.
rd (00101):

Specifies the destination register as a0 (x10).

Operation
The addi instruction performs the following:

a0 = x0 + 0
Since x0 is always 0, the result is simply:

a0 = 0

The instruction li a0, 0 (translated to addi a0, x0, 0) sets the value of the a0 register to 0. This is commonly used to initialize or reset a register to zero.

Instruction 10

![Screenshot_from_2025-01-15_20-50-28 1](https://github.com/user-attachments/assets/bf0743b7-3f42-425d-871b-eba29f966692)

Breakdown of Instruction:
The addi (add immediate) instruction adds an immediate value to the contents of a source register and stores the result in a destination register. In this case, it increments the stack pointer (sp) by 16.

Explanation
Opcode (0010011):

Identifies this as an addi (add immediate) instruction.
Immediate (16):

12-bit signed immediate value to be added to the source register.
rs1 (00010):

Specifies the source register as sp (x2).
funct3 (000):

Specifies addition operation for addi.
rd (00010):

Specifies the destination register as sp (x2).

Operation
The addi instruction performs the following:

sp = sp + 16
It increments the stack pointer by 16. This is commonly used to deallocate space on the stack after a function completes its execution.

The instruction addi sp, sp, 16 increments the stack pointer (sp) by 16, effectively undoing a previous stack allocation. This is often used at the end of a function to restore the stack pointer to its original value.

instruction 11

![Screenshot_from_2025-01-15_20-50-33 1](https://github.com/user-attachments/assets/b3c15573-a443-432e-b14d-e1429ef2a0ae)


Final Answer for 100dc: 00008067 ret
Breakdown of Instruction:
The ret instruction is a pseudoinstruction in RISC-V that translates to a base instruction jalr. Specifically:

ret => jalr x0, 0(ra)

Explanation
Opcode (1100111):

Identifies this as a jalr (jump and link register) instruction.
Immediate (0):

Specifies an offset of 0 to add to the base address in ra.
rs1 (00001):

Specifies the source register as ra (x1), which contains the return address.
funct3 (000):

Specifies the jalr operation.
rd (00000):

Specifies the destination register as x0. Since writes to x0 are ignored, no value is saved.
Operation
The jalr instruction performs the following:

Sets the program counter (PC) to the value in ra plus the offset (0 in this case).
Does not write a link address back to any register, as rd is set to x0.

The instruction ret (translated to jalr x0, 0(ra)) causes the program to return to the address stored in the ra register. This is typically used at the end of a function to return control to the caller.

instruction 12

![Screenshot_from_2025-01-15_20-49-17 1](https://github.com/user-attachments/assets/3611d093-3103-4b6b-ac55-816d7a93bf11)

Instruction: lui a0, 0x21
lui: Load Upper Immediate. This instruction loads a 16-bit immediate value into the upper 16 bits of a register, setting the lower 16 bits to zero.
a0: This is the destination register. In the MIPS calling convention, a0 is typically used as the first argument register for function calls.
0x21: This is the 16-bit immediate value to be loaded into the upper half of a0.
Execution:
The value 0x21 is shifted left by 16 bits and stored in a0.
The result in a0 will be:
𝑎0 = 0𝑥00210000

This instruction is commonly used to set up a base value in a register for further operations, like addressing or arithmetic.

Instruction 13

Instruction: auipc a5, 0xffff0
auipc: "Add Upper Immediate to PC". This instruction computes an address relative to the current program counter (PC) by adding the immediate value (shifted left by 12 bits) to the PC and stores the result in the specified register.
a5: The destination register. In RISC-V, a5 is typically used as a temporary register.
0xffff0: The 20-bit immediate value to be added to the PC.
Execution:
Immediate Shifted: The immediate value 0xffff0 is left-shifted by 12 bits, resulting in 0xffff000.

Addition to PC: The shifted value is added to the PC (current instruction address, 0x100e0 in this case).

Calculation:

Result=PC+(Immediate<<12)
Substituting:
Result=0x100e0+0xffff000
The result is stored in register a5.

Value in a5:
Adding the values:

a5=0x100e0+0xffff000=0x1000000e0
Since the high bits might be truncated depending on the RISC-V implementation (e.g., 32-bit vs. 64-bit architecture), ensure this is interpreted correctly in the context of your program.

Instruction 14

Instruction: beqz a5, 100f8
beqz: This is shorthand for "branch if equal to zero", which checks if the value in the register is zero and branches to a specified address if true.
a5: The register being checked. If the value in a5 is zero, the branch will occur.
100f8: The target address to branch to if the condition is met. In this case, it is 100f8, an offset relative to the current program counter (PC).
Execution:
Condition Check:

The processor evaluates whether the value in a5 is equal to 0.
Branch Behavior:

If a5 == 0: The program counter (PC) is set to the target address 100f8, and execution continues there.
If a5 != 0: The program continues with the next instruction at 100ec.

If this is part of a function, it might be checking whether a5 was successfully computed or initialized earlier (e.g., from a prior auipc or lui operation). If not, it jumps to an alternative path at 100f8, such as an error handler or cleanup code.

Instruction 15 

Instruction: j 1022c
j: This is a jump instruction, an unconditional branch that modifies the program counter (PC) to the specified address.
1022c: This is the target address to jump to, which in this case is 0x1022c.
Execution:
The instruction causes an unconditional jump to the address 1022c, meaning that the program counter (PC) will be set directly to 0x1022c, and the execution continues from there.

Context:
This type of jump is typically used for branching to another part of the program, such as transferring control to a function (atexit in this case, as indicated in the comment), or exiting the current execution flow. It doesn't depend on any condition, so the jump always happens.









