
## Stack

>A **stack** is a linear data structure that stores data following the **Last In, First Out (LIFO)** principle — the last element **pushed** (added) to the stack is the first one to be **popped** (removed).

 This means the last item pushed (added) onto the stack is the first one to be popped (removed).

You can imagine a stack like a pile of plates: you add plates on top and remove plates from the top only.

Stacks are widely used in computer architecture for managing function calls, local variables, expression evaluation, and temporary data storage.

**Stack addressing** is a mode where the operand for an instruction is implicitly located at the top of the stack. The CPU uses a special register called the **Stack Pointer (SP)** to keep track of the top element of the stack

>The **Stack Pointer (SP)** holds the memory address of the current top of the stack.

- When data is pushed onto the stack, SP is updated to point to the new top. 
- When data is popped from the stack, SP is updated to point to the new top after removal.

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

## Ascending/descending

- Descending Stack (Most Common)
	- The stack **grows downward** in memory addresses.
	- The Stack Pointer starts at a high memory address and **decrements** as items are pushed.
	- For example, if SP starts at address `4001`, the first item is stored at `4000`, the next at `3999`, and so forth.
	- This means newer items are at lower memory addresses.
    

- Ascending Stack

	- The stack **grows upward** in memory addresses.
	- The Stack Pointer starts at a low address and **increments** as items are pushed.
	- New items are stored at increasing memory addresses.

## Full/empty

- A **full stack** means the stack has reached its maximum capacity — no more items can be pushed without overwriting other memory or causing errors.
    
- An **empty stack** means there are no items to pop; the stack pointer points to the initial position before any data was pushed.
