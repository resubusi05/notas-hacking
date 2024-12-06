# Retos picoCTF

# Level reverse_cipher

## Objetivo
We have recovered a [binary] and a [text file]Can you reverse the flag.
## Solucion
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ mkdir rc
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ cd rc
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ wget https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ wget https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ file rev_this
rev_this: ASCII text, with no line terminators
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ chmod +x rev
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ ./rev
No flag found, please make sure this is run on the server
Segmentation fault (core dumped)
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ cat rev_this
picoCTF{w1{1wq84fb<1>49}porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ gdb -q rev
Reading symbols from rev...
(No debugging symbols found in rev)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  puts@plt
0x0000000000001040  fread@plt
0x0000000000001050  fclose@plt
0x0000000000001060  fputc@plt
0x0000000000001070  fopen@plt
0x0000000000001080  exit@plt
0x0000000000001090  __cxa_finalize@plt
0x00000000000010a0  _start
0x00000000000010d0  deregister_tm_clones
0x0000000000001100  register_tm_clones
0x0000000000001140  __do_global_dtors_aux
0x0000000000001180  frame_dummy
0x0000000000001185  main
0x00000000000012d0  __libc_csu_init
0x0000000000001330  __libc_csu_fini
0x0000000000001334  _fini
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001185 <+0>:     push   %rbp
   0x0000000000001186 <+1>:     mov    %rsp,%rbp
   0x0000000000001189 <+4>:     sub    $0x50,%rsp
   0x000000000000118d <+8>:     lea    0xe74(%rip),%rsi        # 0x2008
   0x0000000000001194 <+15>:    lea    0xe6f(%rip),%rdi        # 0x200a
   0x000000000000119b <+22>:    call   0x1070 <fopen@plt>
   0x00000000000011a0 <+27>:    mov    %rax,-0x18(%rbp)
   0x00000000000011a4 <+31>:    lea    0xe68(%rip),%rsi        # 0x2013
   0x00000000000011ab <+38>:    lea    0xe63(%rip),%rdi        # 0x2015
   0x00000000000011b2 <+45>:    call   0x1070 <fopen@plt>
   0x00000000000011b7 <+50>:    mov    %rax,-0x20(%rbp)
   0x00000000000011bb <+54>:    cmpq   $0x0,-0x18(%rbp)
   0x00000000000011c0 <+59>:    jne    0x11ce <main+73>
   0x00000000000011c2 <+61>:    lea    0xe57(%rip),%rdi        # 0x2020
   0x00000000000011c9 <+68>:    call   0x1030 <puts@plt>
   0x00000000000011ce <+73>:    cmpq   $0x0,-0x20(%rbp)
   0x00000000000011d3 <+78>:    jne    0x11e1 <main+92>
   0x00000000000011d5 <+80>:    lea    0xe7e(%rip),%rdi        # 0x205a
   0x00000000000011dc <+87>:    call   0x1030 <puts@plt>
   0x00000000000011e1 <+92>:    mov    -0x18(%rbp),%rdx
   0x00000000000011e5 <+96>:    lea    -0x50(%rbp),%rax
   0x00000000000011e9 <+100>:   mov    %rdx,%rcx
   0x00000000000011ec <+103>:   mov    $0x1,%edx
   0x00000000000011f1 <+108>:   mov    $0x18,%esi
   0x00000000000011f6 <+113>:   mov    %rax,%rdi
--Type <RET> for more, q to quit, c to continue without paging--q
Quit
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ nano solve.py
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed/rc$ python3 solve.py
picoCTF{r3v3rs36ad73964}


flag: picoCTF{r3v3rs36ad73964}
## Referencias


