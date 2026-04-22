---
name: 'Task 7: Exception generation mechanisms'
about: Task 7 for Students
title: 'Task 7: Exception generation mechanisms'
labels: enhancement
assignees: ''

---

**Description**

Create the `except()` microarchitecture function implementation, then
add in invocations of machine exceptions in the indicated locations
for privilege mode violations, illegal opcode exception and access
control violation.

**Suggested Solution**

For part 1 of the task, start by copying the `trap()` microarchitecture
function declaration and implementation to a new function called
`except()`.  The functions work identically, the only real difference
being that the `except()` needs to look up the address to change the
`RPC` to from the exception vector table.

**Additional Requirements**

- You are required to cause access control violations for any address read
  or written below user space 0x3000 or for any address accessed in the
  device space above 0xFDFF.
