---
name: 'Task 3: MCR clock run latch'
about: Task 3 for Students
title: 'Task 3: MCR clock run latch'
labels: enhancement
assignees: ''

---

**Description**

Implement helper functions to access and manipulate the memory mapped
Machine Control Register (MCR) run latch bit.

1. `enable_clock()` is a `void` function that takes no parameters.  This
   function should simply set the MCR bit [15] to 1 in order to enable the
   system run latch.  You are required to use the `reg[]` mapping to access
   MCR from this function.
2. `disable_clock()` is also a `void` function with no parameters, and it
  should do the opposite and set the MCR bit [15] to 0.
3. `is_running()` is a function that returns a `bool` result by testing
  the MCR run latch bit [15].  It should return `true` if the clock is
  currently enabled and thus the system is running, and `false` if not.
  We will later be using this function to control the fetch-decode-execute
  loop termination.

Make sure that you add in the correct function prototype declaration into
the `lc3vm.h` file first, and then implement the function with the correct
function documentation in `lc3vm.c`.

**Suggested Solution**


**Additional Requirements**

- You are required to implment all of these as regular c functions for this
  task.
- You are required to use the `reg[]` mapping of the MCR to access and set
  the bit in these functions.
