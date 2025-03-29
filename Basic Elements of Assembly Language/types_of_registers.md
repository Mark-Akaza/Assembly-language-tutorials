
## **Types of Registers in 8086 Assembly**

In **8086 microprocessor**, registers are classified into different types based on their purpose.

---

### **1. General-Purpose Registers (GPRs)**
These registers are used for arithmetic, logic, and data movement operations.

| Register | Description | Special Uses |
|----------|------------|--------------|
| **AX** (Accumulator) | Primary register for arithmetic and I/O operations | Used in multiplication, division, and input/output |
| **BX** (Base) | Used to store memory addresses | Often used as a base pointer for addressing memory |
| **CX** (Count) | Used as a loop counter | Used in `LOOP` instruction and shift/rotate operations |
| **DX** (Data) | Stores extra data in operations | Used in multiplication, division, and I/O operations |

#### ✅ Example: Using AX and BX for Addition
```assembly
MOV AX, 5
MOV BX, 3
ADD AX, BX  ; AX = 5 + 3 = 8
```

---

### **2. Segment Registers**
Segment registers store the base addresses of different memory segments.

| Register | Description |
|----------|------------|
| **CS (Code Segment)** | Holds the segment address of the currently executing code |
| **DS (Data Segment)** | Holds the segment address of the data (variables, constants) |
| **SS (Stack Segment)** | Holds the segment address of the stack (for function calls, interrupts) |
| **ES (Extra Segment)** | Additional data segment used for special operations (like string operations) |

#### ✅ Example: Setting Up DS in EMU8086
```assembly
MOV AX, CS  ; Load code segment address
MOV DS, AX  ; Set DS = CS
```

---

### **3. Pointer and Index Registers**
These registers are used for memory addressing and stack operations.

| Register | Description | Usage |
|----------|------------|-------|
| **SP (Stack Pointer)** | Points to the top of the stack | Used in function calls and `PUSH`/`POP` |
| **BP (Base Pointer)** | Points to a location in the stack | Used for accessing function parameters |
| **SI (Source Index)** | Used for string and memory operations | Works with `DS` by default |
| **DI (Destination Index)** | Used for string and memory operations | Works with `ES` by default |

#### ✅ Example: Using SP and BP in Stack Operations
```assembly
MOV BP, SP  ; Save stack pointer (for accessing parameters in procedures)
```

---

### **4. Special-Purpose Registers**
These registers are used for control, status, and flags.

| Register | Description |
|----------|------------|
| **IP (Instruction Pointer)** | Holds the address of the next instruction to be executed |
| **FLAGS Register** | Stores condition flags (Zero flag, Carry flag, etc.) |

#### ✅ Common Flags in FLAGS Register
| Flag | Meaning |
|------|---------|
| **ZF (Zero Flag)** | Set if the result of an operation is zero |
| **CF (Carry Flag)** | Set if there is a carry/borrow in arithmetic operations |
| **SF (Sign Flag)** | Set if the result is negative |
| **OF (Overflow Flag)** | Set if the result is too large for the destination |

#### ✅ Example: Checking Zero Flag After Subtraction
```assembly
MOV AX, 5
SUB AX, 5  ; AX = 5 - 5 = 0
JZ LABEL   ; Jump to LABEL if Zero Flag (ZF) is set
```

---

### **📌 Summary of Register Types**
| **Register Type** | **Registers** | **Purpose** |
|------------------|-------------|-----------|
| **General-Purpose Registers** | AX, BX, CX, DX | Arithmetic, logic, data transfer |
| **Segment Registers** | CS, DS, SS, ES | Memory segmentation |
| **Pointer & Index Registers** | SP, BP, SI, DI | Stack and memory addressing |
| **Special Registers** | IP, FLAGS | Control and status |

---
