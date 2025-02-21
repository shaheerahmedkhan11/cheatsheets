# x64 Assembly Language Cheatsheet

## General Purpose Registers
- `RAX`, `RBX`, `RCX`, `RDX`: 64-bit general purpose registers
- `EAX`, `EBX`, `ECX`, `EDX`: Lower 32 bits of RAX, RBX, RCX, RDX
- `AX`, `BX`, `CX`, `DX`: Lower 16 bits of RAX, RBX, RCX, RDX
- `AH`, `AL`, `BH`, `BL`, `CH`, `CL`, `DH`, `DL`: Lower 8 bits of AX, BX, CX, DX (AH/AL are the high/low byte of AX, etc.)

## Additional Registers
- `RSI`: Source Index
- `RDI`: Destination Index
- `RBP`: Base Pointer
- `RSP`: Stack Pointer
- `RIP`: Instruction Pointer

## Segment Registers
- `CS`: Code Segment
- `DS`: Data Segment
- `SS`: Stack Segment
- `ES`: Extra Segment
- `FS`, `GS`: Additional segments

## Flags Register (RFLAGS)
- `CF`: Carry Flag
- `PF`: Parity Flag
- `AF`: Auxiliary Carry Flag
- `ZF`: Zero Flag
- `SF`: Sign Flag
- `TF`: Trap Flag
- `IF`: Interrupt Enable Flag
- `DF`: Direction Flag
- `OF`: Overflow Flag

## Common Instructions

### Data Transfer
- `MOV destination, source`: Moves data from source to destination
- `PUSH source`: Pushes source onto the stack
- `POP destination`: Pops value from stack into destination

### Arithmetic
- `ADD destination, source`: Adds source to destination
- `SUB destination, source`: Subtracts source from destination
- `MUL source`: Multiplies RAX by source
- `IMUL source`: Signed multiply RAX by source
- `DIV source`: Divides RDX:RAX by source
- `IDIV source`: Signed divide RDX:RAX by source
- `INC destination`: Increments destination by 1
- `DEC destination`: Decrements destination by 1

### Logic
- `AND destination, source`: Bitwise AND
- `OR destination, source`: Bitwise OR
- `XOR destination, source`: Bitwise XOR
- `NOT destination`: Bitwise NOT
- `SHL destination, count`: Shift left logical
- `SHR destination, count`: Shift right logical
- `SAL destination, count`: Shift left arithmetic
- `SAR destination, count`: Shift right arithmetic

### Control Flow
- `JMP label`: Unconditional jump to label
- `JE label`: Jump if equal (ZF = 1)
- `JNE label`: Jump if not equal (ZF = 0)
- `JG label`: Jump if greater (ZF = 0 and SF = OF)
- `JL label`: Jump if less (SF ≠ OF)
- `JGE label`: Jump if greater or equal (SF = OF)
- `JLE label`: Jump if less or equal (ZF = 1 or SF ≠ OF)
- `CALL label`: Call subroutine
- `RET`: Return from subroutine

### String Operations
- `MOVS`: Move string data
- `CMPS`: Compare string data
- `SCAS`: Scan string data
- `LODS`: Load string data
- `STOS`: Store string data

### Stack Operations
- `PUSHF`: Push flags register onto stack
- `POPF`: Pop flags register from stack
- `ENTER`: Create stack frame for procedure
- `LEAVE`: Remove stack frame for procedure

### Miscellaneous
- `NOP`: No operation
- `HLT`: Halt the processor
- `INT n`: Software interrupt
- `IRET`: Return from interrupt

## Example Code

### Hello World (Linux x64)
```assembly
section .data
    hello db 'Hello, world!', 0

section .text
    global _start

_start:
    ; Write to stdout
    mov rax, 1          ; syscall number (sys_write)
    mov rdi, 1          ; file descriptor (stdout)
    mov rsi, hello      ; pointer to message
    mov rdx, 13         ; message length
    syscall             ; call kernel

    ; Exit program
    mov rax, 60         ; syscall number (sys_exit)
    xor rdi, rdi        ; exit code 0
    syscall             ; call kernel
```

Remember that Assembly language syntax and instructions may vary depending on the processor architecture (e.g., x64, ARM) and the assembler being used (e.g., NASM, MASM).