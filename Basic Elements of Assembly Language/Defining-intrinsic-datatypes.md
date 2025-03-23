 


# 📘 Assembly Language - Defining Data (Notes)

---

## 🟢 **3.4.1 Intrinsic Data Types**

- **Intrinsic Data Types**: Built-in types provided by MASM, mainly defined by their **size in bits**.
  
| Type    | Size (bits) | Description |
|--------|------------|--------------------------------------------|
| BYTE   | 8          | Unsigned 8-bit integer                     |
| SBYTE  | 8          | Signed 8-bit integer                       |
| WORD   | 16         | Unsigned 16-bit integer (or Near pointer)   |
| SWORD  | 16         | Signed 16-bit integer                      |
| DWORD  | 32         | Unsigned 32-bit integer (or Near pointer)   |
| SDWORD | 32         | Signed 32-bit integer                      |
| FWORD  | 48         | 48-bit integer (Far pointer)               |
| QWORD  | 64         | 64-bit integer                             |
| TBYTE  | 80         | 80-bit integer                             |
| REAL4  | 32         | 32-bit IEEE short real (float)             |
| REAL8  | 64         | 64-bit IEEE long real (double)             |
| REAL10 | 80         | 80-bit IEEE extended real                  |

- **Note**: These types **don’t force data interpretation**, they just describe storage size. E.g., `DWORD` can store int, float, pointer, etc.

---

## 🟢 **3.4.2 Data Definition Statement**

### **Purpose:**
- Allocates space in memory for variables.
  
### **Syntax:**
```
[name] directive initializer [, initializer]...
```

### **Example:**
```assembly
count DWORD 12345
```
- **Name** → Optional variable name (must follow identifier rules).
- **Directive** → Specifies type (BYTE, WORD, DWORD, etc.).
- **Initializer** → Actual value assigned (can be constant, expression, or `?` for uninitialized).

---

### **Legacy Data Directives (Supported in NASM & TASM too):**

| Directive | Usage                      |
|---------|-----------------------------|
| DB      | Define Byte (8-bit)          |
| DW      | Define Word (16-bit)         |
| DD      | Define Double Word (32-bit)  |
| DQ      | Define Quad Word (64-bit)    |
| DT      | Define Ten-byte (80-bit)     |

---

## 🟢 Defining BYTE and SBYTE Data**

### **BYTE (8-bit unsigned)**:
```assembly
value1 BYTE 'A'   ; character constant
value2 BYTE 0     ; smallest unsigned byte
value3 BYTE 255   ; largest unsigned byte
```

### **SBYTE (8-bit signed)**:
```assembly
value4 SBYTE -128 ; smallest signed byte
value5 SBYTE +127 ; largest signed byte
```

---

### **Uninitialized Variable:**
```assembly
value6 BYTE ?  ; uninitialized, assigned later at runtime
```

---

### **Offsets Example:**
```assembly
value1 BYTE 10h  ; offset = 0000
value2 BYTE 20h  ; offset = 0001 (auto adjusted)
```

---

### **Using DB for bytes:**
```assembly
val1 DB 255     ; unsigned byte
val2 DB -128    ; signed byte
```

---

## 🟢 **Multiple Initializers:**
```assembly
arr1 DB 10, 20, 30, 40
```
➡️ Allocates 4 bytes initialized to `10, 20, 30, 40`.

---

# 🔥 **Quick Summary:**

| Concept                 | Purpose                                                                 |
|------------------------|-------------------------------------------------------------------------|
| **Intrinsic Data Types**| Define size & type (BYTE, WORD, DWORD, etc.)                              |
| **Data Definition**     | Allocate memory space with optional name & value                         |
| **Legacy Directives**   | DB, DW, DD, DQ, DT                                                       |
| **BYTE/SBYTE**          | 8-bit data (unsigned/signed)                                             |
| **Uninitialized Data**  | Use `?` to leave data uninitialized                                      |
| **Multiple Initializers**| You can initialize arrays easily                                        |

---
