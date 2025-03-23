📚 Basics of Assembly Language
Welcome to the Basics of Assembly Language!
This document covers the fundamental elements you need to start writing and understanding Assembly Language programs.

Table of Contents
Integer Constants

Integer Expressions.md

Real Number Constants.md

Character Constants.md

String Constants.md

Reserved Words.md

Identifiers.md

Directives.md

Instructions.md

NOP (No Operation) Instruction.md



1️⃣ Integer Constants
Whole numbers used in programs.

Can be represented in:

Decimal (e.g., 25)

Hexadecimal (e.g., 0x1A, 1Ah)

Binary (e.g., 1010b)

Octal (e.g., 037o)



2️⃣ Integer Expressions
Combine integer constants using operators:

+, -, *, /, MOD, AND, OR

Example:

assembly
Copy
Edit
MOV AX, 5 + 3



3️⃣ Real Number Constants
Represent fractional numbers (floating-point).

Example:

Copy
Edit
3.14, -0.5


4️⃣ Character Constants
Single character enclosed in single quotes.

Example:

arduino
Copy
Edit
'A', 'b'
Stored as ASCII values.


5️⃣ String Constants
Sequence of characters enclosed in double quotes.

Example:

arduino
Copy
Edit
"Hello", "World!"


6️⃣ Reserved Words
Words predefined by the assembler.

Examples:

Instructions: MOV, ADD, SUB

Directives: DB, DW, END

Registers: AX, BX, SI

Operators: AND, OR, NOT

Cannot be used as variable names.

7️⃣ Identifiers
Names for variables, labels, or constants.

Rules:

Start with a letter.

Can include letters, numbers, and underscores (_).

Must not be a reserved word.

Example:

Copy
Edit
count, total_sum, loop1



8️⃣ Directives
Commands for the assembler, not for CPU execution.

Control how the program is structured.

Examples:

DB (Define Byte)

DW (Define Word)

SEGMENT, ENDS, END




9️⃣ Instructions
Actual commands executed by CPU.

Categories:

Data Transfer: MOV, XCHG

Arithmetic: ADD, SUB, MUL

Logical: AND, OR, XOR

Control Flow: JMP, CALL




🔟 NOP (No Operation) Instruction
NOP = No Operation

Does nothing, consumes 1 CPU cycle.

Used for:

Timing adjustments

Instruction alignment

Debugging / Patching


