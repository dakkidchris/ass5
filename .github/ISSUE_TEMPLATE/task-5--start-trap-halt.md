---
name: 'Task 5: Halt trap clock disable'
about: Task 5 for Students
title: 'Task 5: Halt trap clock disable'
labels: enhancement
assignees: ''

---

**Description**

Modify the main `start()` fetch-decode-execute function to
use the new MCR run latch mechanism.  This task tests that
the trap service routines are working to call a simple
halt trap service routine, that will disable the clock
and thus stop the machine execution.

**Suggested Solution**


**Additional Requirements**

- You are required to reuse your `is_running()` method in the
  `start()` function to test the clock run latch.

