# Retos picoCTF

# Level asm4

## Objetivo
What will asm4("picoCTF_f97bb") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. Source
## Solucion
´´´
┌──(kali㉿kali)-[~/asm4]
└─$ ls    
solve  solve.c  test.S
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ rm solve  
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ rm solve.c        
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ vim solve.c
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ gcc -masm=intel -m32 solve.c -o solve   
solve.c: Assembler messages:
solve.c:6: Error: bad expression
solve.c:6: Error: junk `asm*27' after expression
solve.c:6: Error: bad expression
solve.c:6: Error: junk `asm*23' after expression
solve.c:6: Error: bad expression
solve.c:6: Error: junk `asm*138' after expression
solve.c:6: Error: bad expression
solve.c:6: Error: junk `asm*51' after expression
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ rm solve.c
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ vim solve.c
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ gcc -masm=intel -m32 solve.c -o solve
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ ./solve
0x265
                                                                                     
┌──(kali㉿kali)-[~/asm4]
└─$ cat solve.c 
#include <stdio.h>
#include <stdlib.h>
int asm4(char* in)
{
    int val;
    asm (
        "nop;"
        "nop;"
        "nop;"
        //"push   ebp;"
        //"mov    ebp,esp;"
        "push   ebx;"
        "sub    esp,0x10;"
        "mov    DWORD PTR [ebp-0x10],0x27a;"
        "mov    DWORD PTR [ebp-0xc],0x0;"
        "jmp    asm_27;"
    "asm_23:"
        "add    DWORD PTR [ebp-0xc],0x1;"
    "asm_27:"
        "mov    edx,DWORD PTR [ebp-0xc];"
        "mov    eax,DWORD PTR [%[pInput]];"
        "add    eax,edx;"
        "movzx  eax,BYTE PTR [eax];"
        "test   al,al;"
        "jne    asm_23;"
        "mov    DWORD PTR [ebp-0x8],0x1;"
        "jmp    asm_138;"
    "asm_51:"
        "mov    edx,DWORD PTR [ebp-0x8];"
        "mov    eax,DWORD PTR [%[pInput]];"
        "add    eax,edx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  edx,al;"
        "mov    eax,DWORD PTR [ebp-0x8];"
        "lea    ecx,[eax-0x1];"
        "mov    eax,DWORD PTR [%[pInput]];"
        "add    eax,ecx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  eax,al;"
        "sub    edx,eax;"
        "mov    eax,edx;"
        "mov    edx,eax;"
        "mov    eax,DWORD PTR [ebp-0x10];"
        "lea    ebx,[edx+eax*1];"
        "mov    eax,DWORD PTR [ebp-0x8];"
        "lea    edx,[eax+0x1];"
        "mov    eax,DWORD PTR [%[pInput]];"
        "add    eax,edx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  edx,al;"
        "mov    ecx,DWORD PTR [ebp-0x8];"
        "mov    eax,DWORD PTR [%[pInput]];"
        "add    eax,ecx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  eax,al;"
        "sub    edx,eax;"
        "mov    eax,edx;"
        "add    eax,ebx;"
        "mov    DWORD PTR [ebp-0x10],eax;"
        "add    DWORD PTR [ebp-0x8],0x1;"
    "asm_138:"
        "mov    eax,DWORD PTR [ebp-0xc];"
        "sub    eax,0x1;"
        "cmp    DWORD PTR [ebp-0x8],eax;"
        "jl     asm_51;"
        "mov    eax,DWORD PTR [ebp-0x10];"
        "add    esp,0x10;"
        "pop    ebx;"
        //"pop    ebp;"
        //"ret    ;"
        "nop;"
        "nop;"
        "nop;"
            :"=r"(val)
            : [pInput] "m"(in)
    );
    
    return val;
}

int main(int argc, char** argv)
{
    printf("0x%x\n", asm4("picoCTF_f97bb"));
    
    return 0;
}
        
´´´

## Referencias


