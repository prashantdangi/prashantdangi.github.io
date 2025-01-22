---
title: "Buffer Overflows and The Virtual memory layout"
excerpt: " To understand Stack-buffer-overflow attack in the virtual memory"
categories: Binary-Exploitation

---

# What is Virtual Memory Layout

Operating System manages memory for programs using virtual memory, which is referred as the **virtual memory layout**. Programs are given their own virtual address space, isolating them from other programs.

Below is the representation of the Virtual memory layout 

![Virtual memory layout](/assets/images/Virtual_memory_layout.png)

# Parts of Virtual Memory Address

This layout typically includes:

* **Text Segment :** Holds Compiled Program code.
* **Data Segment :** Holds global and static variables.
* **Heap :** For Dynamically allocated memory during runtime 

  **and**

* **The Stack :** For local variables, function calls and control flow 

# Stack expands in opposite dirction to the data, text and Heap 

## The Call Stack and x86_64 Calling Convention

```
function one(){
    two();
}

function two(){
    three();
}

function three(){
    console.trace("Call Stack");
}
```

function three() execute firsts then --> two() then --> one()

![](/assets/images/function.png)

When a new function is called, we create a new function stack at the top, and pop it off when we are done. All programs are linear like this, you must pop off the top function before revisiting the data contained in the previous functions. If we want to fetch data from other function, it must be **global(.bss or .data)** and not on Stack.

## Function Stacks

> Opcode/Operational Code: Single instruction executed by CPU
>> RBP: Base pointer in x86_64\
>> RSP: Stack pointer in x86_64\
>> RIP: Instruction register in x86_64

![](/assets/images/functioncall.png)

For Setting up the Function Stack, All the parameters are placed in appropriate registers 

### What happens when we call a function

* Opcode "call" pushes the return address onto the stack,
* Opcode "push" pushes RBP onto the stack,
* Opcode "mov" moves RSP to RBP

**This sets up the stack frame for new function**

### Now What happens when exiting a function

* Setting RAX register to desired value,
* Opcode "mov" or "leave" sets RSP to RBP,
* Opcode "pop" pops saved base pointer into RBP 
* Opcode "ret" pops return address into RIP, redirects code execution

# Buffer Overflow 

```
#include <stdio.h>

int main(){
    long overflow_me = 0;
    char buf[0x20]; //0x20 = 32 bits

    gets(buf);

    printf("%ld\n", overflow_me);

    return 0;
}

```

In this program get(buf) is set to take only 32 bits of data, but there is no limitation that the code will only take 32 bits of data and not more than that, if we provide more data (there is no mitigation to that here). So,

Overwriting the return address and base pointer messes up the execution of the program and the code gets corrupted causing **Buffer Overflow**

For Example :

In this code: 

```
void win(){
    printf("You win! If you get here\n");
}

int main(){
    char buf[32];
    
    gets(buf);

    return 0;
}
```

Just like before it can accept 32 bits of data. but if we provide it with more than 32 bits of data it overwrites the base pointer. And now we can go to our intended destination (win offset)

![](/assets/images/offset.png)

**If memory can be corrupted through a vulnerability, control flow and data in memory can be manipulated**