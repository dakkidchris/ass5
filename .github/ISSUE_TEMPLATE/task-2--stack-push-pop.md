---
name: 'Task 2: Implement PSR priority mode and privilege levels'
about: Task 2 for Students
title: 'Task 2: Implement PSR priority mode and privilege levels'
labels: enhancement
assignees: ''

---

**Description**

Implement helper function for machine architecutre to manipulate the current system
stack in use by the running program.  The address of the top of the stack by convention will
be in `R6`.  Also by convention the stack grows towards 0, so when an item is pushed you will
need to decreass the stack pointer by 1, and when the stack is popped you will need to increase
the stack address by 1.

1. Implement `push()`, which will take an `uint16_t` value as its input parameter (and it is a `void` function).
   This method assumes that `R6` is pointing to the top of the current stack in use.
   Subtract 1 from the stack address in R6 to grow the stack, and then place the
   parameter that was pushed into memory that is now pointed to as the top of the
   stack by `R6`.  You are required to reuse the `mem_write()` function here, as
   we later need to add in checks that we are not accessing privileged memory
   when in user mode.
2. You also need to implement `pop()` which takes no parameters and is also a
   `void` function.  This function should pop off the value from the top of the stack.
   To do this you simply need to add 1 to the current value of the `R6` register holding
   the current stack pointer.

Make sure that you add in the correct function prototype declaration into
the `lc3vm.h` file first, and then implement the function with the correct
function documentation in `lc3vm.c`.

**Suggested Solution**


**Additional Requirements**

- You are required to implment all of these as regular c functions for this
  task.
- You are required to use `uint16_t` types for the parameters passed in for the
  value pushed onto the stack.
- You are required to reuse the `mem_write()` function in your implementation of
  `push()`
