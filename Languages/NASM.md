# Register System

Registers:
- segment registers
- general-purpose registers
- special registers

### Segment registers
Segment registers (CS, DS, SS, ES, GS, and FS) are not used in the “flat” memory model.
### General-purpose registers
#### 32-bit:

| EAX | EBX | ECX | EDX | ESI | EDI | EBP | ESP |
| --- | --- | --- | --- | --- | --- | --- | --- |

#### 16-bit:  
In each 32-bit register, a distinct lower half (the lower 16 bits) is defined, which has a separate name obtained by dropping the letter E. In other words, it is also possible to operate on the 16-bit registers AX, BX, CX, DX, SI, DI, BP, and SP, which represent the lower halves of the corresponding 32-bit registers.

| AX  | BX  | CX  | DX  | SI  | DI  | BP  | SP  | 
| --- | --- | --- | --- | --- | --- | --- | --- |

#### 8-bit:
The AX, BX, CX, and DX registers are further subdivided into lower and upper parts, which are now 8-bit wide. The remaining general-purpose registers do not have such distinct one-byte subregisters.

| AH  | BH  | CH  | DH  |
| --- | --- | --- | --- |
| AL  | BL  | CL  | DL  | 
#### Register names:
- AX - accumulator
- BX - base
- CX - counter
- DX - data
- SI - source index
- DI - destination index
- BP - base pointer
- SP - stack pointer
### Special registers
- EIP - instruction pointer
- FLAGS - flag register
#### FLAGS register
- ZF - zero flag
- CF - carry flag
- SF - sign flag
- OF - overflow flag
- DF - direction flag
- PF - parity flag
- AF - auxiliary carry flag
- IF - interrupt flag
- TF - trap flag

## Registers table:

| 64-bit register | 32-bit sub-register | 16-bit sub-register | 8-bit sub-register |
| --------------- | ------------------- | ------------------- | ------------------ |
| rax             | eax                 | ax                  | al                 |
| rbx             | ebx                 | bx                  | bl                 |
| rcx             | ecx                 | cx                  | cl                 |
| rdx             | edx                 | dx                  | dl                 |
| rsi             | esi                 | si                  | sil                |
| rdi             | edi                 | di                  | dil                |
| rbp             | ebp                 | bp                  | bpl                |
| rsp             | esp                 | sp                  | spl                |
| r8              | r8d                 | r8w                 | r8b                |
| r9              | r9d                 | r9w                 | r9b                |
| r10             | r10d                | r10w                | r10b               |
| r11             | r11d                | r11w                | r11b               |
| r12             | r12d                | r12w                | r12b               |
| r13             | r13d                | r13w                | r13                |
| r14             | r14d                | r14w                | r14b               |
| r15             | r15d                | r15w                | r15b               |

32-bit:
![[Pasted image 20260127141223.png]]

# Segments
Three main segments:
- code segment(.text)
- data segment
	- Initialized data section(.data)
	- Uninitialized data section(.bss)
- stack segment

![[Pasted image 20260127144944.png]]
# Memory allocation directives
The assembler translates instruction mnemonics into binary code, forming a data array that is subsequently interpreted by the central processing unit (CPU) as a sequence of instructions. Program control is carried out by loading the address of the entry point into the instruction pointer register.
### Structure of memory sections
To organize data and code within a program, specialized sections are used, which are declared using the section directive:
- .text: Contains executable machine code.
- .data: Intended for initialized data whose values are fixed at compile time and embedded into the executable file image.
- .bss: Reserves space for uninitialized variables. Only information about the required size of this section is stored in the object file, which optimizes the file size on disk.
### Memory management directives
The assembler (in particular, NASM) provides tools for memory allocation based on standard data units:

| Unit type   | Size(byte) | Directives (Data/BSS) |
| ----------- | ---------- | --------------------- |
| Byte        | 1          | db/resb               |
| Word        | 2          | dw/resw               |
| Double Word | 4          | dd/resd               |
| Quad Word   | 8          | dq/resq               | 
#### Directives for reserving uninitialized memory
These directives instruct the assembler to allocate a specified number of memory cells, without specifying any content other than the quantity.
- resb
- resw
- resd
- resq

A label is usually placed before a memory reservation directive.
Example:
```nasm
string resb 20
count  resw 256
x      resd 1
```