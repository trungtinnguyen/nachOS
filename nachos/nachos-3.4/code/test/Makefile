# use normal make for this Makefile
#
# Makefile for building user programs to run on top of Nachos
#
# Several things to be aware of:
#
#    Nachos assumes that the location of the program startup routine (the
# 	location the kernel jumps to when the program initially starts up)
#       is at location 0.  This means: start.o must be the first .o passed 
# 	to ld, in order for the routine "Start" to be loaded at location 0
#

# if you are cross-compiling, you need to point to the right executables
# and change the flags to ld and the build procedure for as

GCCDIR = ../../../cross-compiler/decstation-ultrix/bin/

LDFLAGS = -T script -N

ASFLAGS = -mips2

CPPFLAGS = $(INCDIR)

# if you aren't cross-compiling:

# GCCDIR =

# LDFLAGS = -N -T 0

# ASFLAGS =

# CPPFLAGS = -P $(INCDIR)

PATH = $(GCCDIR):/lib:/usr/bin:/bin

CC = $(GCCDIR)gcc -B../../../cross-compiler/

AS = $(GCCDIR)as

LD = $(GCCDIR)ld

CPP = gcc -E

INCDIR =-I../userprog -I../threads

CFLAGS = -G 0 -c $(INCDIR)

all: halt shell matmult sort ReadInt PrintInt ascii BubSort PrintString Help CreateFile echo cat copy alpha number par

start.o: start.s ../userprog/syscall.h
	$(CPP) $(CPPFLAGS) start.c > strt.s
	$(AS) $(ASFLAGS) -o start.o strt.s
	rm strt.s

halt.o: halt.c
	$(CC) $(CFLAGS) -c halt.c
halt: halt.o start.o
	$(LD) $(LDFLAGS) start.o halt.o -o halt.coff
	../bin/coff2noff halt.coff halt

shell.o: shell.c
	$(CC) $(CFLAGS) -c shell.c
shell: shell.o start.o
	$(LD) $(LDFLAGS) start.o shell.o -o shell.coff
	../bin/coff2noff shell.coff shell

sort.o: sort.c
	$(CC) $(CFLAGS) -c sort.c
sort: sort.o start.o
	$(LD) $(LDFLAGS) start.o sort.o -o sort.coff
	../bin/coff2noff sort.coff sort

matmult.o: matmult.c
	$(CC) $(CFLAGS) -c matmult.c
matmult: matmult.o start.o
	$(LD) $(LDFLAGS) start.o matmult.o -o matmult.coff
	../bin/coff2noff matmult.coff matmult

ReadInt.o: ReadInt.c
	$(CC) $(CFLAGS) -c ReadInt.c
ReadInt: ReadInt.o start.o
	$(LD) $(LDFLAGS) start.o ReadInt.o -o ReadInt.coff
	../bin/coff2noff ReadInt.coff ReadInt

PrintInt.o: PrintInt.c
	$(CC) $(CFLAGS) -c PrintInt.c
PrintInt: PrintInt.o start.o
	$(LD) $(LDFLAGS) start.o PrintInt.o -o PrintInt.coff
	../bin/coff2noff PrintInt.coff PrintInt


PrintChar.o: PrintChar.c
	$(CC) $(CFLAGS) -c PrintChar.c
PrintChar: PrintChar.o start.o
	$(LD) $(LDFLAGS) start.o PrintChar.o -o PrintChar.coff
	../bin/coff2noff PrintChar.coff PrintChar

ascii.o: ascii.c
	$(CC) $(CFLAGS) -c ascii.c
ascii: ascii.o start.o
	$(LD) $(LDFLAGS) start.o ascii.o -o ascii.coff
	../bin/coff2noff ascii.coff ascii

BubSort.o: BubSort.c
	$(CC) $(CFLAGS) -c BubSort.c
BubSort: BubSort.o start.o
	$(LD) $(LDFLAGS) start.o BubSort.o -o BubSort.coff
	../bin/coff2noff BubSort.coff BubSort

PrintString.o: PrintString.c
	$(CC) $(CFLAGS) -c PrintString.c
PrintString: PrintString.o start.o
	$(LD) $(LDFLAGS) start.o PrintString.o -o PrintString.coff
	../bin/coff2noff PrintString.coff PrintString

Help.o: Help.c
	$(CC) $(CFLAGS) -c Help.c
Help: Help.o start.o
	$(LD) $(LDFLAGS) start.o Help.o -o Help.coff
	../bin/coff2noff Help.coff Help

CreateFile.o: CreateFile.c
	$(CC) $(CFLAGS) -c CreateFile.c
CreateFile: CreateFile.o start.o
	$(LD) $(LDFLAGS) start.o CreateFile.o -o CreateFile.coff
	../bin/coff2noff CreateFile.coff CreateFile


echo.o: echo.c
	$(CC) $(CFLAGS) -c echo.c
echo: echo.o start.o
	$(LD) $(LDFLAGS) start.o echo.o -o echo.coff
	../bin/coff2noff echo.coff echo

cat.o: cat.c
	$(CC) $(CFLAGS) -c cat.c
cat: cat.o start.o
	$(LD) $(LDFLAGS) start.o cat.o -o cat.coff
	../bin/coff2noff cat.coff cat


copy.o: copy.c
	$(CC) $(CFLAGS) -c copy.c
copy: copy.o copy.o
	$(LD) $(LDFLAGS) start.o copy.o -o copy.coff
	../bin/coff2noff copy.coff copy


alpha.o: alpha.c
	$(CC) $(CFLAGS) -c alpha.c
alpha: alpha.o alpha.o
	$(LD) $(LDFLAGS) start.o alpha.o -o alpha.coff
	../bin/coff2noff alpha.coff alpha

number.o: number.c
	$(CC) $(CFLAGS) -c number.c
number: number.o number.o
	$(LD) $(LDFLAGS) start.o number.o -o number.coff
	../bin/coff2noff number.coff number

par.o: par.c
	$(CC) $(CFLAGS) -c par.c
par: par.o par.o
	$(LD) $(LDFLAGS) start.o par.o -o par.coff
	../bin/coff2noff par.coff par


