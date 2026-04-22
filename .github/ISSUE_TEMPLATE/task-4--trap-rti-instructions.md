---
name: 'Task 4: Implement trap and rti instructions'
about: Task 4 for Students
title: 'Task 4: Implement trap and rti instructions'
labels: enhancement
assignees: ''

---

**Description**

For part 1 of the task, implement the new version of the `trap()` function.

The pseudocode given in A.2 for the `trap` instruction is as follows:

```
TEMP = PSR;
if (PSR[15] == 1) // e.g. if currently in user mode
    USP = R6 and R6 = SSP 
    PSR[15] = 0 // change to supervisor mode now
push PC
push TEMP // push PC and the original PSR on stack
PC = mem[ZEXT(trapvect8)];
```


Then for part 2 implement the corresponding `rti()` function.

The pseudocode given for `rti` in appendix A.2 of the Patt and Patel book is:

```
if (PSR[15] == 1) // if we are in user mode you can invoke rti
  Initiate a privilege mode exception

PSR = mem[R6]   // R6 is the SSP, the PSR is restored
pop
PC = mem[R6]    // R6 is the SSP, PC is restored
pop      

if (PSR[15] == 1) // we did a mode switch back to user mode
   SSP = R6 and R6 = USP
```

Both of these functions were already declared and empty stubs
provided for this assignment, you simply need to complete
the full implementaiton now.

**Suggested Solution**


**Additional Requirements**

- You are required to reuse the `is_user_mode()` and `supervisor_mode()`
  functions to test and switch from user mode to supervisor mode.
- Likewise you need to use the `push()` method to push on the PSR and the
  PC to the system stack.
- You are required to push the PC first then the original PSR, so that
  the PSR ends up on top of stack, and the return PC below it.
- As shown in the pseudocode, you need to save the PSR before
  switching to supervisor mode, the PSR that is pushed on needs to be
  what it was when the function is called.
- There is a `TRP` macro defined in `lc3vm.h` that you can and should use
  to extract the low 8 trap vector bits from the instruction.
- You are required to use `read_memory()` here to look up the trap
  service routine address in memory using the `trapvect8` bits of the
  instruction.

- You are again required to use the `pop()` methods to manipulate
  the system stack for `rti()` as well.
- And you should be using `mem_read()` to read the `PSR` and `RPC`
  values when restoring them from the stack for `rti()`
