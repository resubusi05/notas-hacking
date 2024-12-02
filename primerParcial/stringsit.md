# Retos picoCTF

# Level strings it

## Objetivo
Can you find the flag in file without running it?

## Solución
```
┌──(kali㉿kali)-[~/Downloads/stringsit]
└─$ file strings 
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=0cdedfba33422d235dba8c90e00fb77b235f1ff8, not stripped
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/stringsit]
└─$ strings strings | grep 'pico'
picoCTF{5tRIng5_1T_7f766a23}
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/stringsit]
└─$ chmod 777 strings 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/stringsit]
└─$ ./strings 
Maybe try the 'strings' function? Take a look at the man page

```
## Notas adicionales

## Referencias


