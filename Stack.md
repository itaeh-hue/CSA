## Stack

>A **stack** is a linear data structure that stores data following the **Last In, First Out (LIFO)** principle — the last element **pushed** (added) to the stack is the first one to be **popped** (removed).

You can imagine a stack like a pile of plates: you add plates on top and remove plates from the top only.

In computer systems, a **stack** is a reserved area of memory used to store temporary data such as:
- Return addresses when calling subroutines (functions)
- Local variables
- CPU register states during interrupts or context switches

The CPU uses a special register called the **Stack Pointer (SP)** to keep track of the current top of the stack.

Stacks can be divided into two types:

- **Ascending Stack:**
	- The stack grows towards higher memory addresses. 
	- When you *push* data, the SP _increases_.

- **Descending Stack:**
	- The stack grows towards lower memory addresses. 
	- When you *push* data, the SP _decreases_.

>Registers like **SP (Stack Pointer)** and **PC (Program Counter)** are 16-bit, meaning they hold 16-bit (2-byte) values.
- **PC** holds the address of the next instruction to execute.  
- **SP** holds the address of the top of the stack in memory.

When we say that memory is **byte-addressed**, we mean that each address points to a single byte.
- Since registers are 16-bit, they hold 2 bytes, which might be stored in two consecutive memory addresses.
