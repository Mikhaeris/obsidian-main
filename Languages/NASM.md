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
# Директивы для отведения памяти
Написанные нами условные обозначения машинных команд ассемблер транслирует в некий образ области памяти массив чисел (данных), которые нужно будет записать в смежные ячейки оперативной памяти. Затем при запуске программы в эту область памяти будет передано управление (то есть адрес какой-то из этих ячеек будет записан в регистр ЕІР) и центральный процессор начнёт выполнение нашей программы, используя числа из созданного ассемблером образа в качестве кодов команд.

Аналогично можно использовать ассемблер для создания образа области памяти, содержащей данные, а не команды. Для этого нужно сообщить ассемблеру, сколько памяти нам требуется под те или иные нужды, и при этом, возможно, задать те значения, которые в эту память будут помещены перед стартом программы.

Пользуясь нашими указаниями, ассемблер сформирует отдельно образ памяти, содержащей команды (образ секции text), и отдельно образ памяти, содержащей инициализированные данные (образ секции data), а кроме того, сосчитает, сколько нам нужно такой памяти, о начальном значении которой мы не беспокоимся, так что для неё не нужно формировать образ, а нужно лишь указать общий объём (размер секции. bss). Всё это ассемблер запишет в файл с объектным кодом, а компоновщик из таких файлов (возможно, нескольких) сформирует исполняемый файл, содержащий, кроме собственно машинного кода, во-первых, те данные, которые нужно записать в память перед стартом программы, и, во-вторых, указания на то, сколько программе понадобится ещё памяти, кроме той, что нужна под размещение машинного кода и исходных данных. Чтобы сообщить ассемблеру, в какой секции должен быть размещён тот или иной фрагмент формируемого образа памяти, мы в программе на языке ассемблера должны использовать директиву section; например, строчка
section .text
означает, что результат обработки последующих строк должен размещаться в секции кода, а строчка
section.bss
заставляет ассемблер перейти к формированию секции неинициализированных данных. Директивы переключения секций могут встречаться в программе сколько угодно раз мы можем сформировать часть одной секции, затем часть другой, потом вернуться к формированию первой.
Сообщить ассемблеру о наших потребностях в оперативной памяти мож-но с помощью директив резервирования памяти, которые делятся на два вида: директивы резервирования неинициализированной памяти и ди-рективы задания исходных данных. Обычно перед директивами обоих видов ставится метка, чтобы можно было ссылаться с её помощью на адрес в па-мяти, где ассемблер отвёл для нас требуемые ячейки.
Директивы резервирования памяти (обоих видов) в ассемблере NASM ис-пользуют в качестве единиц измерения объёма памяти байты, слова, а так-же двойные и учетверённые слова. Но в данном случае нужно учитывать, что слово обозначает два байта.

