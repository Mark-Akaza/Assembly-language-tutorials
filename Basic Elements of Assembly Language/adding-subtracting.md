Here’s a clean, GitHub-friendly **README.md** continuation for the next section on **Adding and Subtracting Integers**, following the same style.  
You can place this inside the **"Basics of Assembly Language"** folder or as a separate folder like **"Arithmetic Operations"**, depending on how you'd like to organize.

---

# ➕➖ Adding and Subtracting Integers in Assembly Language

This section explains how to perform basic arithmetic operations, particularly **addition** and **subtraction** of integers, using Assembly Language instructions.

---

## 3.2 Adding and Subtracting Integers

### 🔹 ADD Instruction
- **Purpose**: Adds two integers.
- Syntax:
  ```assembly
  ADD destination, source
  ```
  Example:
  ```assembly
  MOV AX, 5
  ADD AX, 3   ; AX = AX + 3 → Result: AX = 8
  ```

### 🔹 SUB Instruction
- **Purpose**: Subtracts one integer from another.
- Syntax:
  ```assembly
  SUB destination, source
  ```
  Example:
  ```assembly
  MOV AX, 10
  SUB AX, 4   ; AX = AX - 4 → Result: AX = 6
  ```

### 🟢 Important Notes:
- The result is stored in the **destination** operand.
- The **flags** (Zero, Carry, Sign, Overflow) are affected, useful for conditional jumps.

---

## 3.2.1 Alternative Version of AddSub

- You can use different **registers** or **immediate values** to perform addition/subtraction.
  
Example:
```assembly
MOV AL, 7
MOV BL, 2
ADD AL, BL   ; AL = AL + BL → Result: AL = 9
SUB BL, 1    ; BL = BL - 1  → Result: BL = 1
```

- You can also subtract larger numbers using **AX**, **BX**, **CX**, or **DX** registers.

---

## 3.2.2 Program Template

A simple program structure for addition & subtraction:

```assembly
.model small
.stack 100h

.data
    num1 DW 5
    num2 DW 3
    result DW ?

.code
main PROC
    MOV AX, @data
    MOV DS, AX

    MOV AX, num1
    ADD AX, num2
    MOV result, AX  ; result = num1 + num2

    SUB AX, num2
    MOV result, AX  ; result = num1 again after subtraction

    MOV AH, 4CH
    INT 21H
main ENDP
END main
```

---

## 3.2.3 Section Review

### ✔️ Key Points:
- `ADD` & `SUB` instructions manipulate integer values directly in CPU registers.
- Always ensure proper register usage to avoid overwriting data.
- Flags are automatically updated after arithmetic operations.
- Template helps in structuring small arithmetic programs.

---

## 📌 Summary

**Addition and subtraction** are essential operations in Assembly, laying the foundation for more complex arithmetic and logical operations.  
By mastering these, you can build calculators, counters, and more advanced algorithms.

---

---
