# Retos picoCTF

# Level Bit-O-Asm-2

## Objetivo
Can you figure out what is in the eax register? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Download the assembly dump here.

## Solucion
picoCTF{}

```
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2024-11-24 22:21:16--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt               100%[===========================================================================>]     270  --.-KB/s    in 0s      

2024-11-24 22:21:18 (15.5 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-2]
└─$ ls    
disassembler-dump0_b.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-2]
└─$ 
```

Cada dígito hexadecimal representa un múltiplo de potencias de 16.
De derecha a izquierda:

E = 14 en decimal 

A=10 en decimal

Con esto vemos el valor de la bandera, que es 654874

## Referencias


