# Retos picoCTF

# Level Need for speed

## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? 
## Solucion
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ cd needforspeed
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ wget https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ ls -la need-for-speed
-rw-r--r-- 1 porti_04 porti_04 8888 Oct 26  2020 need-for-speed
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ chmod +x need-for-speed
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ ./need-for-speed
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/needforspeed$ gdb -q need-for-speed
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x00000000000005d8  _init
0x0000000000000600  putchar@plt
0x0000000000000610  puts@plt
0x0000000000000620  alarm@plt
0x0000000000000630  __sysv_signal@plt
0x0000000000000640  exit@plt
0x0000000000000650  __cxa_finalize@plt
0x0000000000000660  _start
0x0000000000000690  deregister_tm_clones
0x00000000000006d0  register_tm_clones
0x0000000000000720  __do_global_dtors_aux
0x0000000000000760  frame_dummy
0x000000000000076a  decrypt_flag
0x00000000000007f1  calculate_key
0x000000000000080e  alarm_handler
0x000000000000082f  set_timer
0x000000000000087d  get_key
0x00000000000008ac  print_flag
0x00000000000008d8  header
0x000000000000091a  main
0x0000000000000960  __libc_csu_init
0x00000000000009d0  __libc_csu_fini
0x00000000000009d4  _fini
(gdb) set disassembly-flavor intel
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   rbp
   0x000000000000091b <+1>:     mov    rbp,rsp
   0x000000000000091e <+4>:     sub    rsp,0x10
   0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000000929 <+15>:    mov    eax,0x0
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    eax,0x0
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    eax,0x0
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    eax,0x0
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    eax,0x0
   0x0000000000000956 <+60>:    leave
   0x0000000000000957 <+61>:    ret
End of assembler dump.
(gdb) b *(main+40)
Breakpoint 1 at 0x942
(gdb) i b
Num     Type           Disp Enb Address            What
1       breakpoint     keep y   0x0000000000000942 <main+40>
(gdb) d 1
(gdb) b *(main+30)
Breakpoint 2 at 0x938
(gdb) run
Starting program: /home/porti_04/pico_retos/reversing/needforspeed/need-for-speed
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================


Breakpoint 2, 0x0000555555400938 in main ()
(gdb) j *(main+35)
The program is not being run.
(gdb) run
Starting program: /home/porti_04/pico_retos/reversing/needforspeed/need-for-speed
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================


Breakpoint 2, 0x0000555555400938 in main ()
(gdb) j *(main+35)
Continuing at 0x55555540093d.
Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
[Inferior 1 (process 18840) exited normally]
(gdb)



flag: PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
## Referencias


