# simple makefile to compile lc3 assembly test objects / programs
LC3ASM=../lc3asm # requires access to an LC-3 assembler to reassemble 
#ASM_FLAGS=-v
ASM_FLAGS=

PROGS=prog-01.exe \
  prog-02.exe \
	prog-03.exe \
	prog-04.exe

LC3OS_OBJS=trap-vector-table.obj \
	exception-vector-table.obj \
	trap-out.obj \
	trap-puts.obj \
	trap-in.obj \
	trap-halt.obj \
	exception-illegal-opcode.obj \
	exception-privilege-mode.obj \
	exception-access-control-violation.obj

.PHONY : all
all : $(PROGS) task5-trap-halt.obj

prog-01.exe : $(LC3OS_OBJS) prog-01.obj
	cat $? > $@

prog-02.exe : $(LC3OS_OBJS) prog-02.obj
	cat $? > $@

prog-03.exe : $(LC3OS_OBJS) prog-03.obj
	cat $? > $@

prog-04.exe : $(LC3OS_OBJS) prog-04.obj
	cat $? > $@

%.obj : %.lc3
	$(LC3ASM) $(ASM_FLAGS) -o $@ $<

.PHONY : clean
clean :
	rm -f *.obj *.exe