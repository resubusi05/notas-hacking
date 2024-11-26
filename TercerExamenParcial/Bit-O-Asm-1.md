# Retos picoCTF

# Level Bit-O-Asm-1

## Objetivo
Can you figure out what is in the eax register? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Download the assembly dump here.

## Solucion
En el registro eax encontramos el numero 0x30 que en decimal es 48

```
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2024-11-23 22:53:34--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt               100%[===========================================================================>]     209  --.-KB/s    in 0s      

2024-11-23 22:53:35 (473 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-1]
└─$ ls -la
total 40
drwxr-xr-x  2 kali kali  4096 Nov 23 22:53 .
drwxr-xr-x 44 kali kali 32768 Nov 23 22:38 ..
-rw-r--r--  1 kali kali   209 Aug  4  2023 disassembler-dump0_a.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-1]
└─$ 


```


## Referencias


