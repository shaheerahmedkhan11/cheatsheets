# Assembly Language Cheatsheet for Linux

## General Syntax
- **Comments**: Start with `;`
- **Labels**: Define with `label_name:`
- **Instructions**: Generally consist of an operation and operands (e.g., `mov eax, 1`)

## Registers
### General Purpose
- `eax`, `ebx`, `ecx`, `edx`
- `esi`, `edi`, `esp`, `ebp`

### Segment Registers
- `cs` (Code Segment)
- `ds` (Data Segment)
- `ss` (Stack Segment)
- `es`, `fs`, `gs`

### Instruction Pointer
- `eip`

## Data Movement
- `mov dest, src` : Move `src` to `dest`
- `push src` : Push `src` onto the stack
- `pop dest` : Pop from stack into `dest`
- `lea dest, src` : Load effective address

## Arithmetic
- `add dest, src` : Add `src` to `dest`
- `sub dest, src` : Subtract `src` from `dest`
- `mul src` : Multiply `eax` by `src`
- `div src` : Divide `eax` by `src`, quotient in `eax`, remainder in `edx`
- `inc dest` : Increment `dest`
- `dec dest` : Decrement `dest`
- `neg dest` : Negate `dest`

## Logical
- `and dest, src` : Bitwise AND
- `or dest, src` : Bitwise OR
- `xor dest, src` : Bitwise XOR
- `not dest` : Bitwise NOT
- `shl dest, count` : Shift left
- `shr dest, count` : Shift right
- `sar dest, count` : Arithmetic shift right

## Control Flow
- `jmp label` : Jump to `label`
- `cmp op1, op2` : Compare `op1` and `op2`
- `je label` : Jump if equal
- `jne label` : Jump if not equal
- `jg label` : Jump if greater
- `jl label` : Jump if less
- `jge label` : Jump if greater or equal
- `jle label` : Jump if less or equal
- `call label` : Call subroutine
- `ret` : Return from subroutine
- `loop label` : Loop to `label` `ecx` times

## System Calls (Linux)
### Making a system call
1. Load syscall number into `eax`
2. Load arguments into `ebx`, `ecx`, `edx`, `esi`, `edi`, `ebp`
3. Execute `int 0x80`

### Common System Calls
- `sys_exit` : `1`
- `sys_fork` : `2`
- `sys_read` : `3`
- `sys_write` : `4`
- `sys_open` : `5`
- `sys_close` : `6`
- `sys_waitpid` : `7`
- `sys_execve` : `11`

### Example: Exit Program
```assembly
mov eax, 1       ; syscall number for sys_exit
mov ebx, 0       ; exit code 0
int 0x80         ; call kernel
```

### Example: Write to stdout
```assembly
mov eax, 4       ; syscall number for sys_write
mov ebx, 1       ; file descriptor 1 (stdout)
mov ecx, msg     ; pointer to message
mov edx, len     ; message length
int 0x80         ; call kernel

section .data
msg db 'Hello, World!', 0xA  ; message
len equ $ - msg              ; message length
```

## Stack Operations
- `push val` : Push value onto stack
- `pop reg` : Pop value from stack into register
- `call func` : Call function (push `eip` onto stack and jump)
- `ret` : Return from function

### Stack Frame
```assembly
push ebp         ; save old base pointer
mov ebp, esp     ; set new base pointer
sub esp, 16      ; allocate space for local variables

; function body

mov esp, ebp     ; deallocate local variables
pop ebp          ; restore old base pointer
ret              ; return to caller
```

## String Operations
- `movs` : Move string data
- `cmps` : Compare string data
- `scas` : Scan string data
- `lods` : Load string data
- `stos` : Store string data
- `rep` : Repeat prefix for string operations

### Example: String Copy
```assembly
section .data
src db 'Source string', 0
dest db 16 dup (0)

section .text
global _start

_start:
    mov esi, src  ; source address
    mov edi, dest ; destination address
    mov ecx, 16   ; number of bytes to copy
    rep movsb     ; repeat move byte
    ; _exit code
    mov eax, 1    ; syscall number for sys_exit
    xor ebx, ebx  ; exit code 0
    int 0x80      ; call kernel
```

## Conditional Instructions
- `sete dest` : Set if equal
- `setne dest` : Set if not equal
- `setg dest` : Set if greater
- `setl dest` : Set if less
- `setge dest` : Set if greater or equal
- `setle dest` : Set if less or equal

### Example: Conditional Move
```assembly
mov eax, 5
mov ebx, 10
cmp eax, ebx
cmovg ecx, eax  ; if eax > ebx, move eax to ecx
cmovle ecx, ebx ; if eax <= ebx, move ebx to ecx
```

## Floating-Point Operations
- `fld` : Load floating-point value
- `fst` : Store floating-point value
- `fadd` : Floating-point addition
- `fsub` : Floating-point subtraction
- `fmul` : Floating-point multiplication
- `fdiv` : Floating-point division
- `fsqrt` : Floating-point square root

### Example: Floating-Point Addition
```assembly
section .data
val1 dd 1.5
val2 dd 2.5
result dd 0.0

section .text
global _start

_start:
    fld dword [val1]  ; load val1
    fld dword [val2]  ; load val2
    fadd              ; add st(0) and st(1)
    fstp dword [result] ; store result

    ; _exit code
    mov eax, 1        ; syscall number for sys_exit
    xor ebx, ebx      ; exit code 0
    int 0x80          ; call kernel
```

## Useful Tips
- Always save and restore registers if using them in your functions
- Use `gdb` for debugging and stepping through your code
- Use `objdump` to disassemble binaries and inspect the generated assembly code

## References
- [x86 Assembly Guide](http://www.cs.virginia.edu/~evans/cs216/guides/x86.html)
- [Linux System Call Table](https://syscalls.w3challs.com/)