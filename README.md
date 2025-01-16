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


