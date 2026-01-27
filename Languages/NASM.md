# Register System

Registers:
- segment registers
- general-purpose registers
- special registers

### Segment registers
Segment registers are not used in the “flat” memory model.

| CS  | DS  | SS  | ES  | GS  | FS  | 
| --- | --- | --- | --- | --- | --- |
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
| r13             | r13d                | r13w                | r13b               |
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
- **.text**: Contains executable machine code.
- **.data**: Intended for initialized data whose values are fixed at compile time and embedded into the executable file image.
- **.bss**: Reserves space for uninitialized variables. Only information about the required size of this section is stored in the object file, which optimizes the file size on disk.
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
#### Directives for specifying initial data
These directives do not merely reserve memory but specify the values that should be present in memory at program startup. The corresponding values are listed separated by commas; memory is allocated according to the number of specified values.
- db
- dw
- dd
- dq

Example:
```nasm
fibon dw 1, 1, 2, 3, 5, 8, 13, 21
```
# Specification of numeric values 
Numeric values can be specified in:
- binary
- octal
- decimal
- hexadecimal
#### Binary
A binary number is indicated by the letter **b** at the end.
```nasm
10011011b
```
#### Octal
Octal numbers are indicated by appending the letter **o** or **q** after the number.
```nasm
634o
754q
```
#### Decimal
Decimal numbers are represented as in standard mathematics.
```nasm
2026
```
#### Hexadecimal
A hexadecimal number can be specified in three ways:
- By appending the letter **h** at the end
	- If the number begins with a letter, a *0* must be placed before the number
- By prefixing the number with the symbol **$**
	- If the number begins with a letter, a *0* must be added
- By prefixing the number with **0x**

Example:
```nasm
2af3h
0a21h

$2af3
$0f9

0x2af3
```
# Text strings
The assembler allows a character to be specified directly by enclosing it in single or double quotation marks instead of using its code.
```nasm
dig7 db '7'
welmsg db 'Welcome to Cyberspace!'
```
Within the context of double quotation marks, apostrophes are treated as literal characters; the same principle applies to the inclusion of double quotation marks within apostrophes.
```nasm
panic db 'So I say: "Don', "'", 't panic"'
```

# Instructions
### The mov instruction
`mov` instruction have two operands:
1. The first operand specifies the location where the data will be stored.
2. The second operand specifies the source from which the data will be taken.

```nasm
mov eax, ebx
```
The mov instruction only copies data without performing any transformations.

### Operands types
Three operands types:
1) **Immediate operand**
	```nasm
	mov edx, 40f2a008h
	```
2) **Register operand**
	```nasm
	mov eax, ebx
	```
3) **Memory (address) operand** 
	```nasm
	section .data
	count dd 0
	
	section .text
	    mov [count], eax
	```
### Indirect addressing
Example:
```nasm
mov ebx, [eax]
```
This means: "Take the value in the EAX register, use this value as an address, access memory at that address, retrieve four bytes from there, and store them in the EBX register."
Otherwise:
```nasm
mov ebx, eax
```
This means: "copy This means: "Copy the contents of the EAX register into the EBX register."
### Effective address
An address at which the next machine instruction will access memory (whether the address is specified explicitly or computed) is called the **effective address**.
The processor allows the effective address to be specified so that it is computed during program execution.

General form of the effective address:
![[Pasted image 20260127171352.png]]

Each of the three components is optional. However, it is important to understand that the expression within the square brackets cannot be arbitrary in any way.
#### The lea instruction
The `lea` instruction allows the processor's capabilities for computing the effective address to be used without accessing memory. The instruction has two operands: the first must be a register, and the second must be a memory-type operand.
```nasm
lea eax, [1000+ebx+8*ecx]
```

### Operand sizes and their permissible combinations
Permissible operand type combinations for the `mov` instruction:
- to register from register
- to memory from register
- to register from memory
- to register from an immediate operand (i.e., from the instruction code)
- to a memory location or memory area from an immediate operand


```nasm
mov [x], 25 ; ERROR!!!
```
To use such an instruction, it is necessary to inform the assembler of the exact operand size by placing a **size specifier** before any of the operands.
- byte
- word
- dword
- qword
```nasm
mov dword [x], 25
```

### Integer addition and subtraction
#### The `add` and `sub` instructions
Addition and subtraction operations on integers are performed using the `add` and `sub` instructions, respectively.  
Both instructions have two operands:
- the first specifies one of the numbers involved in the operation and the location where the result should be stored
- the second operand specifies the other number for the operation (the second addend or the subtrahend). 

For these instructions, the same five forms as for the `mov` instruction are possible.
```nasm
add eax, ebx

sub [x], ecx
```
From an implementation perspective, addition and subtraction of signed and unsigned numbers are performed in exactly the same way.

According to the result obtained, the add and sub instructions set the values of the OF, CF, ZF, and SF flags.

1) The ZF flag is set if the result of the last operation is zero; otherwise, the flag is cleared.
2) The SF flag is set if the result is negative; otherwise, it is cleared (relevant only for signed numbers).
3) The OF flag is set if an overflow occurs, meaning that the sign of the resulting value does not correspond to the mathematically expected sign (relevant only for signed numbers).
4) The CF flag is set if a carry out of the most significant bit occurs, or if a borrow from a non-existent bit takes place (relevant only for unsigned numbers).

#### The `adc` and `sbb` instructions
Addition and subtraction with carry are performed by the `adc` and `sbb` instructions, which take the CF flag into account.

Suppose we have two 64-bit integers, where the first is stored in the EDX (high 32 bits) and EAX (low 32 bits) registers, and the second is similarly stored in the EBX and ECX registers.  
Then, these two numbers can be added using the instructions:
```nasm
add eax, ecx    ; add the lower parts
adc edx, ebx    ; now add the higher parts, taking the carry into account
```
If subtraction is required, it is performed using the instructions:
```nasm
sub eax, ecx    ; subtract the lower parts
sbb edx, ebx    ; now subtract the higher parts, taking the borrow into account
```
#### The `inc` and `dec` instructions
The `inc` and `dec` instructions have a single operand (register or memory type) and perform increment and decrement by one, respectively. Both instructions set the ZF, OF, and SF flags, but do not affect the CF flag. When used with a memory-type operand, an explicit operand size specification is required.
```nasm
mov eax, 0

inc eax       ; now eax store 1
dec eax       ; now eax store 0
```
#### The `neg` instruction
The neg instruction, which also has a single operand, performs sign negation, that is, a "unary minus" operation. It is usually applied to signed numbers; however, it sets all four flags: ZF, OF, SF, and CF.
```nasm
neg eax
```
#### The `cmp` instruction
The cmp instruction performs the same subtraction as the sub instruction, except that the result is not stored anywhere. The instruction is used solely to set the flags, and it is usually followed immediately by a conditional jump instruction. The first operand of the cmp instruction cannot be an immediate value.
```nasm
cmp eax, 10
je  some_label
```
### Integer multiplication and division
All integer multiplication and division instructions have only one operand, which specifies the second factor; this operand can be a register or a memory-type operand, but not an immediate value. The first factor and the dividend, as well as the location for storing the result, are **implicit operands**, represented by the AL, AX, or EAX registers, and, if necessary, the register pairs DX:AX and EDX:EAX.
#### The `mul` and `imul` instructions
The `mul` instruction is used for unsigned integer multiplication, while the `imul` instruction is used for signed multiplication. In both cases, depending on the operand size (the second factor), the first factor is taken from the appropriate register.
|                |           |          |           |

| number of bits | implicit multiplier | product |
| -------------- | ------------------- | ------- |
| 8              | AL                  | AX      |
| 16             | AX                  | DX:AX   |
| 32             | EAX                 | EDX:EAX |

```nasm
mov al, 2
mov bl, 3

mul bl       ; now ax store 6
```

The mul and imul instructions clear the CF and OF flags if the upper half of the result is not effectively used, that is, if all significant bits of the result fit into the lower half. For mul, this means that all bits of the upper half of the result are zero; for imul, it means that all bits of the upper half of the result are equal to the most significant bit of the lower half of the result. Otherwise, both CF and OF are set. The states of the remaining flags after execution are undefined.

#### The `div` and `idiv` instructions
For integer division (and computation of the remainder), the `div` instruction is used for unsigned integers, and `idiv` for signed integers. The single operand of the instruction specifies the divisor. Depending on the bit width of this divisor, the dividend is taken from a register of the corresponding size. The quotient is always rounded toward zero (for unsigned and positive values, toward the smaller value; for negative values, toward the larger value). The sign of the remainder computed by idiv always matches the sign of the dividend, and the absolute value (magnitude) of the remainder is strictly less than the absolute value of the divisor. The values of the flags after integer division are undefined.

| number of bits | divisible | quotient | remainder |
| -------------- | --------- | -------- | --------- |
| 8              | AX        | AL       | AH        |
| 16             | DX:AX     | AX       | DX        |
| 32             | EDX:EAX   | EAX      | EDX       |

```nasm
mov ax, 7
mov bx, 3

div bx       ; now al store 2 and ah store 1
```