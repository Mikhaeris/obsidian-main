# Система регистров

Типы регистров:
- сегментные регистры
- регистры общего назначения
- специальные регистры

### Сегментные регистры
Сегментные регистры в "плоской" модели памяти не используются.

| CS  | DS  | SS  | ES  | GS  | FS  | 
| --- | --- | --- | --- | --- | --- |
### Регистры общего назначения
#### 32-bit:

| EAX | EBX | ECX | EDX | ESI | EDI | EBP | ESP |
| --- | --- | --- | --- | --- | --- | --- | --- |

#### 16-bit:  
В каждом 32-битном регистре выделяется обособленная младшая половина (младшие 16 бит), имеющая отдельные названия, получаемые отбрасыванием буквы E; иначе говоря, мы можем работать также с 16-битными регистрами AX, BX, CX, DX, SI, DI, BP и SP, которые представляют собой младшие половины соответствующих 32-битных регистров.

| AX  | BX  | CX  | DX  | SI  | DI  | BP  | SP  | 
| --- | --- | --- | --- | --- | --- | --- | --- |

#### 8-bit:
Регистры AX, BX, CS и DX также делятся на младшие и старшие части, теперь уже восьмибитные. Остальные регистры общего назначения таких обособленных однобайтовых подрегистров не имеют.

| AH  | BH  | CH  | DH  |
| --- | --- | --- | --- |
| AL  | BL  | CL  | DL  | 
#### Названия регистров:
- AX - accumulator
- BX - base
- CX - counter
- DX - data
- SI - source index
- DI - destination index
- BP - base pointer
- SP - stack pointer
### Специальные регистры
- EIP - instruction pointer
- FLAGS - flag register
#### Флаговый регистр
- ZF - zero flag
- CF - carry flag
- SF - sign flag
- OF - overflow flag
- DF - direction flag
- PF - parity flag
- AF - auxiliary carry flag
- IF - interrupt flag
- TF - trap flag

## Таблица регистров:

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

# Сегменты
Три основных сегмента:
- сегмент кода(.text)
- сегмент данных
	- секция инициализированных данных(.data)
	- секция неинициализированных данных(.bss)
- сегмент стека

![[Pasted image 20260127144944.png]]
# Директивы для отведения памяти
Ассемблер осуществляет трансляцию мнемоник команд в бинарный код, формируя массив данных, который в дальнейшем интерпретируется центральным процессором (ЦП) как последовательность инструкций. Управление программой реализуется путем загрузки адреса точки входа в регистр указателя команд.
### Структура сегмента памяти
Для организации данных и кода внутри программы используются специализированные разделы, объявляемые с помощью директивы section:
- **.text**: Содержит исполняемый машинный код.
- **.data**: Предназначена для инициализированных данных, значения которых определяются на этапе компиляции и включаются в образ исполняемого файла.
- **.bss**: Резервирует пространство для неинициализированных переменных. В объектном файле сохраняется только информация о требуемом размере данного раздела, что позволяет оптимизировать объем файла на диске
### Директивы управления памятью
Ассемблер (в частности, NASM) предоставляет средства распределения памяти на основе стандартных единиц данных:

| Тип данных         | Размер(байты) | Директива (Data/BSS) |
| ------------------ | ------------- | -------------------- |
| Байт               | 1             | db/resb              |
| Слово              | 2             | dw/resw              |
| Двойное слово      | 4             | dd/resd              |
| Учетверенное слово | 8             | dq/resq              |
#### Директивы резервирования неинициализированной памяти
Эти директивы приказывают ассемблеру выделить заданное количество ячеек памяти, причем ничего, кроме количества, не уточняется.
- resb
- resw
- resd
- resq

Обычно перед директивой резервирования памяти ставится метка.  
Пример:
```nasm
string resb 20
count  resw 256
x      resd 1
```
#### Директивы задания исходных данных
Эти директивы не просто резервируют память, а указывают, какие значения в этой памяти должны находиться к моменту запуска программы. Соответствующие значение указывается после директивы через запятую; памяти отводится столько, сколько указано значений.
- db
- dw
- dd
- dq

Пример:
```nasm
fibon dw 1, 1, 2, 3, 5, 8, 13, 21
```
# Задание числовых значений
Числовые значения могут быть заданы в:
- двоичной
- восьмиричной
- десятичной
- шестнадцатиричной
#### Двоичная
Двоичное число обозначается буквой **b** на конце.
```nasm
10011011b
```
#### Восьмиричная
Восьмиричное число обозначается добавлением после числа буквы **o** или **q** в конце числа. 
```nasm
634o
754q
```
#### Десятичная
Десятичное число обозначается в стандартной математической форме.
```nasm
2026
```
#### Шестандцатиричная
Шестнадцатиричное число может быть задано тремя сособами:
- Добавление буквы **h** на конец слова
	- Если число начинается с буквы, то цифра *0* должна быть поставлена в конце числа
- Добавлением символа **$** в начало числа
	- Если число начинается с буквы, то цифра *0* должна быть добавлена в начало числа
- Добавлением перед числом символов **0x**

Пример:
```nasm
2af3h
0a21h

$2af3
$0f9

0x2af3
```
# Текстовые строки
Ассемблер позволяет вместо кода написать сам символ, взяв его в апострофы или двойные кавычки.
```nasm
dig7 db '7'
welmsg db 'Welcome to Cyberspace!'
```
Внутри двойных кавычек апострофы рассматриваются как обычный символ; то же самое можно сказать и о символе двойных кавычек внутри апострофов.
```nasm
panic db 'So I say: "Don', "'", 't panic"'
```

# Команды
### Команда `mov`
Команда `mov` имеет два операнда:
1) Первый операнд задает то место, куда будут помещены данные.
2) Второй операнд то, откуда данные будут взяты.

```nasm
mov eax, ebx
```
Команда `mov` только копирует данные, не выполняя никаких преобразований. Для преобразований данных существуют другие команды.

### Виды операндов
Есть три вида операндов:
1) **Непосредственный операнд**
	```nasm
	mov edx, 40f2a008h
	```
2) **Регистровый операнд**
	```nasm
	mov eax, ebx
	```
3) **Адресный операнд / операнд типа "память"** 
	```nasm
	section .data
	count dd 0
	
	section .text
	    mov [count], eax
	```
### Косвенная адресация
Пример:
```nasm
mov ebx, [eax]
```
Это означает: "Возьми значение в регистре EAX, используй это значение в качестве адреса, по этому адресу обратись к памяти, возьми оттуда четыре байты и занеси их в регистр EBX."
В противоположность:
```nasm
mov ebx, eax
```
Это означает: "Скопируй содержимое регистра EAX в регистр EBX."
### Исполнительный адрес
Адрес, по которому очередная машинная команда произведет обращение к памяти (неважно, задан этот адрес явно или вычислен) называется исполнительным адресом.
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
If the divisor contains the value zero at the time the div or idiv instruction is executed, the processor triggers a so-called exception, also referred to as an internal interrupt, as a result of which control is transferred to the operating system. In most cases, the operating system reports an error and terminates the current task as abnormal. The same behavior occurs if the result of the division does not fit into the allocated bit width.
#### Integer extension
When performing integer division of signed numbers, it is often necessary to extend the dividend before the division.

Instructions:
- `cbw` (convert byte to word) - extends the value in the AL register to AX
- `cwd` (convert word to doubleword) - extends the value in the AX register to DX:AX
- `cwde` (convert word to dword, extended) - extends the value in the AX register to EAX
- `cdq` (convert dword to qword) - Extends the value in the EAX register to EDX:EAX

Note that for division of unsigned integers, special instructions for extending the bit width are not required: it is sufficient to simply clear the higher part of the dividend, whether it be AH, DH, or EDX.
### Conditional and unconditional jumps
The normal sequential execution of instructions can be altered by performing a **control transfer**, also referred to as a **jump**; a control-transfer instruction forcibly writes a new address into the EIP register, causing the processor to continue program execution from a different location.

The instructions are classified as follows:
- **Unconditional jumps** – perform a control transfer to another location in the program without any checks.
- **Conditional jumps** – may, depending on the result of a certain condition, either transfer control to a specified location or not perform the transfer.

Control-transfer instructions are classified into three types depending on the “distance” of the transfer:
- **Far jumps**(`far`) imply a control transfer to a program fragment located in a different segment. Since under the Unix operating system we use a “flat” memory model, such jumps are unnecessary because there are simply no other segments.
- **Near jumps**(`near`) are control transfers to an arbitrary location within a single segment; essentially, these jumps represent an explicit change of the EIP value. In the “flat” memory model, this is the type of jump used to reach any location within our address space.
- **Short jumps**(`short`) are used for optimization when the target location is no more than 127 bytes ahead or 128 bytes behind the current instruction. In machine code, the offset for such an instruction is encoded in a single byte, which imposes the corresponding limitation.

The type of jump can be specified explicitly by placing the word `short` or `near` after the instruction (the assembler also recognizes the word `far`, of course, but we don't need it).

The **unconditional jump** instruction is called `jmp`. The instruction has a single operand, which specifies the address to which control should be transferred. Most often, the jmp instruction is used with an immediate operand, that is, an address specified directly in the instruction; naturally, this is not a numeric address, which is usually unknown, but a label.
It is also possible to use a register operand (in this case, the jump is made to the address contained in the register) or a memory-type operand (the address is read from a double word located at a specified memory location); such jumps are called indirect, in contrast to direct jumps, where the address is specified explicitly.
```nasm
jmp cycle    ; Jump to the label cycle
jmp eax      ; Jump to the address contained in the EAX register
jmp [addr]   ; Jump to the address stored in memory labeled addr

jmp [eax]    ; Jump to the address read from memory
             ; located at the address contained in the EAX register
```
Here, the first instruction specifies a direct jump, while the remaining instructions specify indirect jumps.

**Conditional jump** instructions are supported by the processor in a wide variety: a jump can be performed depending on the value of a single flag, a combination of flags, or even the value of a register.

It is important to note that, unlike unconditional jump instructions, conditional jump instructions are considered short by the assembler by default if the type of jump is not specified explicitly. Another nontrivial point is that all conditional jump instructions allow only an immediate operand (usually a label). The address for such a jump cannot be taken from a register or from memory.
### Construction of branches and loops
A standard Pascal-style loop with a precondition
```pascal
while <condition> do <body>
```
is implemented using machine instructions according to the following scheme:
```nasm
cycle:   <evaluate condition>
         JNx cycle_quit        ; exit
         <execute body>
         JMP cycle             ; repeat
cycle_quit:
```
and branching in its full form
```pascal
if <condition> then <branch1> else <branch2>
```
is transformed into:
```nasm
         <evaluate condition>
         JNx else_branch       ; to the else branch
         <execute branch1>
         JMP if_quit           ; bypassing the else branch
else_branch:
         <execute branch2>
if_quit:
```