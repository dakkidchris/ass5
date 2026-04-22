---
name: 'Task 6: KBSR and DSR status update on memory access'
about: Task 6 for Students
title: 'Task 6: KBSR and DSR status update on memory access'
labels: enhancement
assignees: ''

---

**Description**

Add the following logic to the `mem_read()`
function:

```
if address is KBDR_ADDR
    clear KBSR[15]
```


And add the following lotic to the `mem_write()`
function:

```
if address is DDR_ADDR
    clear DSR[15]
```

**Suggested Solution**



**Additional Requirements**

- You need to test the address against the `KBDR_ADDR` to see if
  the bit should be cleared
- But you should be using the `iomap[KBSR]` when manipulating
  and clearing the keyboard status bit.
- Make sure you update the `KBSR` bit before reading and returning the asked
  for value.
- As hinted at again you should be using the defined `DDR_ADDR`
  when testing if the display data register is receiving a new
  character.
- And also use `iomap[DSR]` to manipulate and clear the display
  status register bit.
