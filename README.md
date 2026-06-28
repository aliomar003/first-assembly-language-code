# First Assembly Language Code

## Objective

The objective of this activity is to write a simple Assembly language program using NASM in Linux that displays text on the screen.

## Flowchart

Start
↓
Store message text
↓
Use system call to print message
↓
Exit program
↓
End

## Challenges

One challenge I encountered was understanding the structure of an Assembly program, especially the `.data` and `.text` sections. I also had to make sure the line breaks printed correctly after each sentence.

## Assembly Code

```asm
section .data
    message db "I came,", 10, "I saw,", 10, "I conquered.", 10
    length equ $ - message

section .text
    global _start

_start:
    mov eax, 4
    mov ebx, 1
    mov ecx, message
    mov edx, length
    int 0x80

    mov eax, 1
    mov ebx, 0
    int 0x80
```

## Output

```text
I came,
I saw,
I conquered.
```
