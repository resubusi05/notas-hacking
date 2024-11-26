# Retos picoCTF

# Level ASCII FTW

## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.
You can download the file from here.

## Solucion
```
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ wget https://artifacts.picoctf.net/c/506/asciiftw                    
--2024-11-23 20:42:52--  https://artifacts.picoctf.net/c/506/asciiftw
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16752 (16K) [application/octet-stream]
Saving to: ‘asciiftw’

asciiftw                               100%[===========================================================================>]  16.36K  --.-KB/s    in 0.005s  

2024-11-23 20:42:53 (3.36 MB/s) - ‘asciiftw’ saved [16752/16752]

                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ ls -la       
total 56
drwxr-xr-x  2 kali kali  4096 Nov 23 20:42 .
drwxr-xr-x 43 kali kali 32768 Nov 23 17:45 ..
-rw-r--r--  1 kali kali 16752 May  9  2023 asciiftw
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ ./asciiftw   
zsh: permission denied: ./asciiftw
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ chmod 777 asciiftw 
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ ./asciiftw        
The flag starts with 70
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ file asciiftw 
asciiftw: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=c29491782ee13aa7c5734d77b281865b608e46e9, for GNU/Linux 3.2.0, not stripped
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ gdb ./asciiftw                           
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
Reading symbols from ./asciiftw...
(No debugging symbols found in ./asciiftw)
(gdb) layout next
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ gdb ./asciiftw
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
Reading symbols from ./asciiftw...
(No debugging symbols found in ./asciiftw)
(gdb) layout next
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/ASCIIFTW]
└─$ 

```

al usar gdb nos damos cuenta que se guarda una cadena de texto en la pila, al traducir esta cadena a ascii nos da la bandera: picoCTF{ASCII_IS_EASY_3CF4BFAD}


## Referencias


