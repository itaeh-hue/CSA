

## Memory layout

Prior to diving into the principles of memory allocation in Linux, it is first necessary to understand how memory works from the perspective of a process.  

When you start a program, regardless of the language in which it's written, the OS creates a process and allocates virtual memory address space for it. This memory is divided into several regions, each with a specific purpose, arranged into a *memory layout*. 

Linux memory layout:

- Text segment (aka code segment of text)
	- The text segment stores binary instructions of the program. 
	- This area is read-only, which prevents the program from modifying its own code.
	- Additionally, the text segment can be shared among multiple processes (through a mechanism called [shared memory](https://medium.com/@0xtr1gger/a-deep-dive-into-linux-memory-management-understanding-virtual-memory-and-beyond-7455955bab78)).

- Initialized data segment
	- A part of virtual memory of the process that stores variables whose values are initialized (i.e., variables assigned to a value).

- Uninitialized data segment, aka BSS (Block Started by Symbol)
	- The BSS segment, named after an ancient assembler operator, contains uninitialized variables (whose are not assigned to a value). These variables are automatically assigned to zero at runtime. 

- Heap
	- The heap segment is used for dynamic memory allocation using system calls like `brk()` and `mmap()`.
	- The heap area begins at the end of the BSS segment and grows towards the stack at larger addresses from there.

- Stack
	- The stack is a segment of dynamically changing size used to store local variables, parameters, and return addresses of functions. This segment follows the LIFO (Last In First Out) structure.
	- The stack segment is generally located in the higher addresses of the memory and grows opposite to heap, to lower addresses. 
	- The kernel dynamically allocates memory for the stack when a process starts, and the stack grows or shrinks as the process executes.
	- When stack and heap pointer meet, free memory of the program is said to be exhausted.

- Command-line arguments
	- This area stores arguments passed to a program.

![memory_layout_back](https://github.com/user-attachments/assets/131efaaa-4e63-4c8e-8f42-ad78c4719862)


## Memory allocation

When an application needs memory, it requests it from the kernel using a system call. 



- https://www.scaler.com/topics/c/memory-layout-in-c/


ANSWER
- -https://www.perplexity.ai/search/act-as-a-csa-computer-systems-FaUU5sIIR06TaqwEF9dlbA#2
