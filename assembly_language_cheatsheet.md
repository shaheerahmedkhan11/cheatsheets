# Assembly Language Cheatsheet for x64 Windows Architecture

## General Purpose Registers
- `RAX`: Accumulator register (used in arithmetic operations)
- `RBX`: Base register (used as a pointer to data)
- `RCX`: Counter register (used in loop operations)
- `RDX`: Data register (used in I/O operations)
- `RSI`: Source index register (used in string operations)
- `RDI`: Destination index register (used in string operations)
- `RBP`: Base pointer register (points to the base of the stack)
- `RSP`: Stack pointer register (points to the top of the stack)
- `R8` to `R15`: Additional general-purpose registers

## Segment Registers
- `CS`: Code segment
- `DS`: Data segment
- `SS`: Stack segment
- `ES`: Extra segment
- `FS`: Additional segment
- `GS`: Additional segment

## Instruction Pointer
- `RIP`: Instruction pointer register (points to the next instruction to be executed)

## Flags Register
- `RFLAGS`: Flags register (contains status flags, control flags, and system flags)

## Common Instructions
- `MOV`: Move data from one location to another
  ```assembly
  MOV destination, source
  ```
- `ADD`: Add two values
  ```assembly
  ADD destination, source
  ```
- `SUB`: Subtract two values
  ```assembly
  SUB destination, source
  ```
- `MUL`: Multiply two values
  ```assembly
  MUL source
  ```
- `DIV`: Divide two values
  ```assembly
  DIV source
  ```
- `INC`: Increment a value by 1
  ```assembly
  INC destination
  ```
- `DEC`: Decrement a value by 1
  ```assembly
  DEC destination
  ```
- `PUSH`: Push a value onto the stack
  ```assembly
  PUSH value
  ```
- `POP`: Pop a value from the stack
  ```assembly
  POP destination
  ```
- `CALL`: Call a procedure
  ```assembly
  CALL procedure
  ```
- `RET`: Return from a procedure
  ```assembly
  RET
  ```
- `JMP`: Jump to a specified address
  ```assembly
  JMP address
  ```
- `CMP`: Compare two values
  ```assembly
  CMP destination, source
  ```
- `JE`: Jump if equal
  ```assembly
  JE address
  ```
- `JNE`: Jump if not equal
  ```assembly
  JNE address
  ```
- `JG`: Jump if greater
  ```assembly
  JG address
  ```
- `JL`: Jump if less
  ```assembly
  JL address
  ```

## System Calls
- `SYSCALL`: Make a system call
  ```assembly
  SYSCALL
  ```

## Data Types
- `BYTE`: 8-bit data
  ```assembly
  BYTE value
  ```
- `WORD`: 16-bit data
  ```assembly
  WORD value
  ```
- `DWORD`: 32-bit data
  ```assembly
  DWORD value
  ```
- `QWORD`: 64-bit data
  ```assembly
  QWORD value
  ```

## Example
```assembly
section .data
    msg db "Hello, World!", 0

section .text
    global _start

_start:
    ; Write message to stdout
    mov rax, 1          ; syscall: write
    mov rdi, 1          ; file descriptor: stdout
    mov rsi, msg        ; message to write
    mov rdx, 13         ; message length
    syscall             ; make syscall

    ; Exit program
    mov rax, 60         ; syscall: exit
    xor rdi, rdi        ; exit code: 0
    syscall             ; make syscall
```

This cheatsheet provides a quick reference to the most common instructions and registers used in x64 assembly language programming on Windows architecture.