---
name: 'Task 1: Implement PSR priority mode and privilege levels'
about: Task 1 for Students
title: 'Task 1: Implement PSR priority mode and privilege levels'
labels: enhancement, good first issue
assignees: ''

---

**Description**

For part 1 of the task, implement these functions to manipulate the user/supervisor
mode bit of the PSR:

1. The `is_user_mode()` function should return a `bool` result.  It needs
   to test bit 15 and return `true` if the bit is 1 indicating user mode, and return `false`
   if it is 0 and in supervisor mode.  You need to use masks here as the NZP and priority
   level bits may not always all be 0.
2. `user_mode()` is a `void` function.  It should set the bit 15 of the
   PSR to be 1, leaving all of the other bits unchanged.  The tests
   start by switching into user mode by calling this function.
3. `supervisor_mode()` is also a `void` function that puts the machine
   into supervisor mode by setting bit 15 to 0.

Then for part 2 also add these methods to set and get the priority level
from the PSR:

1. `priority()` returns the current priority level set in the PSR
   priority bits.  This should return an `uint16_t` type.
2. `set_priority()` is used to set the priority bits.  Again pass in
   a `uint16_t` type for the parameter, though we only use the least
   significant 3 bits of this parameter value.

Make sure that you add in the correct function prototype declaration into
the `lc3vm.h` file first, and then implement the function with the correct
function documentation in `lc3vm.c`.

**Suggested Solution**


**Additional Requirements**

- You are required to implment all of these as regular c functions for this
  task.
- You are required to use `uint16_t` types for the parameters passed in to set
  the priority level.
