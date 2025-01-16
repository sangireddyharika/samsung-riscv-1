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
