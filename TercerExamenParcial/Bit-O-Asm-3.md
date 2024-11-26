# Retos picoCTF

# Level Bit-O-Asm-3

## Objetivo
Can you figure out what is in the eax register? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Download the assembly dump here.

## Solucion
picCTF{}2619997

```
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-3]
└─$ wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
--2024-11-25 20:23:09--  https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.26, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 461 [application/octet-stream]
Saving to: ‘disassembler-dump0_c.txt’

disassembler-dump0_c.txt               100%[===========================================================================>]     461  --.-KB/s    in 0s      

2024-11-25 20:23:18 (505 MB/s) - ‘disassembler-dump0_c.txt’ saved [461/461]

                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-3]
└─$ ls
disassembler-dump0_c.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Bit-O-Asm-3]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
               
```

## Referencias


