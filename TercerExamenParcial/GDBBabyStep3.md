# Retos picoCTF

# Level GDB baby step 3

## Objetivo
Now for something a little different. 0x2262c96b is loaded into memory in the main function. Examine byte-wise the memory that the constant is loaded in by using the GDB command x/4xb addr. The flag is the four bytes as they are stored in memory. If you find the bytes 0x11 0x22 0x33 0x44 in the memory location, your flag would be: picoCTF{0x11223344}.
Debug this.

## Solucion
picoCTF{0x6bc96222}

```
                                                                  
┌──(kali㉿kali)-[~/Downloads/GDBBabyStep3]
└─$ file debugger0_c 
debugger0_c: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=a10a8fa896351748020d158a4e18bb4be15cd3aa, for GNU/Linux 3.2.0, not stripped
                                                                  
┌──(kali㉿kali)-[~/Downloads/GDBBabyStep3]
└─$ gdb debugger0_c 
GNU gdb (Debian 15.1-1) 15.1
Copyright (C) 2024 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_c...
(No debugging symbols found in debugger0_c)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)
   0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax
   0x000000000040111f <+25>:    pop    %rbp
   0x0000000000401120 <+26>:    ret
End of assembler dump.
(gdb) x/4xb addr
No symbol table is loaded.  Use the "file" command.
(gdb) break *main+25
Breakpoint 1 at 0x40111f
(gdb) r
Starting program: /home/kali/Downloads/GDBBabyStep3/debugger0_c 
zsh:1: permission denied: /home/kali/Downloads/GDBBabyStep3/debugger0_c
During startup program exited with code 126.
(gdb) quit
                                                                  
┌──(kali㉿kali)-[~/Downloads/GDBBabyStep3]
└─$ chmod 777 debugger0_c 
                                                                  
┌──(kali㉿kali)-[~/Downloads/GDBBabyStep3]
└─$ gdb debugger0_c      
GNU gdb (Debian 15.1-1) 15.1
Copyright (C) 2024 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_c...
(No debugging symbols found in debugger0_c)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)
   0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax
   0x000000000040111f <+25>:    pop    %rbp
   0x0000000000401120 <+26>:    ret
End of assembler dump.
(gdb) break *main+25
Breakpoint 1 at 0x40111f
(gdb) r
Starting program: /home/kali/Downloads/GDBBabyStep3/debugger0_c 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".                                                          

Breakpoint 1, 0x000000000040111f in main ()
(gdb) x/4xb $rbp-4
0x7fffffffdd9c: 0x6b    0xc9    0x62    0x22
(gdb) quit
A debugging session is active.

        Inferior 1 [process 18341] will be killed.

Quit anyway? (y or n) y
                                                                  
┌──(kali㉿kali)-[~/Downloads/GDBBabyStep3]
└─$ 
```
