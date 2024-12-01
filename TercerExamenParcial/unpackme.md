# Retos picoCTF

# Level unpackme

## Objetivo
Reverse engineer this binary.


## Solucion
picoCTF{up><_m3_f7w_77ad107e}

```
─$ objdump -d unpackme-upx | less

                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ strings archivo | grep "picoCTF"                                     
strings: 'archivo': No such file
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ strings unpackme-upx | grep "picoCTF"
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ strings unpackme-upx | grep "pico"   
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx                        
zsh: permission denied: ./unpackme-upx
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ chmod 777 unpackme-upx 
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx        
What's my favorite number? ^[[H
Sorry, that's not it!
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ 
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 4
Sorry, that's not it!
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 1
Sorry, that's not it!
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 2
Sorry, that's not it!
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ objdump -d unpackme-upx              

unpackme-upx:     file format elf64-x86-64


Disassembly of section .init:

0000000000401000 <_init>:
  401000:       f3 0f 1e fa             endbr64
  401004:       48 83 ec 08             sub    $0x8,%rsp
  401008:       48 c7 c0 00 00 00 00    mov    $0x0,%rax
  40100f:       48 85 c0                test   %rax,%rax
  401012:       74 02                   je     401016 <_init+0x16>
  401014:       ff d0                   call   *%rax
  401016:       48 83 c4 08             add    $0x8,%rsp
  40101a:       c3                      ret

Disassembly of section .plt:

0000000000401020 <.plt>:
  401020:       f3 0f 1e fa             endbr64
  401024:       f2 ff 25 ed df 0d 00    bnd jmp *0xddfed(%rip)        # 4df018 <_GLOBAL_OFFSET_TABLE_+0x18>
  40102b:       0f 1f 44 00 00          nopl   0x0(%rax,%rax,1)
  401030:       f3 0f 1e fa             endbr64
  401034:       f2 ff 25 e5 df 0d 00    bnd jmp *0xddfe5(%rip)        # 4df020 <_GLOBAL_OFFSET_TABLE_+0x20>
  40103b:       0f 1f 44 00 00          nopl   0x0(%rax,%rax,1)
  401040:       f3 0f 1e fa             endbr64

```

```
  4b2d1d:       48 89 ef                mov    %rbp,%rdi
  4b2d20:       e8 4b bf f7 ff          call   42ec70 <__free>
  4b2d25:       49 c7 45 08 00 00 00    movq   $0x0,0x8(%r13)
  4b2d2c:       00 
  4b2d2d:       e9 12 ff ff ff          jmp    4b2c44 <free_mem+0x144>
  4b2d32:       4c 89 f7                mov    %r14,%rdi
  4b2d35:       e8 36 bf f7 ff          call   42ec70 <__free>
  4b2d3a:       49 c7 44 24 08 00 00    movq   $0x0,0x8(%r12)
  4b2d41:       00 00 
  4b2d43:       4d 8b 67 08             mov    0x8(%r15),%r12
  4b2d47:       49 8b 0c 24             mov    (%r12),%rcx
  4b2d4b:       48 85 c9                test   %rcx,%rcx
  4b2d4e:       74 8d                   je     4b2cdd <free_mem+0x1dd>
  4b2d50:       31 c0                   xor    %eax,%eax
  4b2d52:       eb 11                   jmp    4b2d65 <free_mem+0x265>
  4b2d54:       0f 1f 40 00             nopl   0x0(%rax)
  4b2d58:       48 83 c0 01             add    $0x1,%rax
  4b2d5c:       48 39 c1                cmp    %rax,%rcx
  4b2d5f:       0f 84 78 ff ff ff       je     4b2cdd <free_mem+0x1dd>
  4b2d65:       48 89 c2                mov    %rax,%rdx
  4b2d68:       48 c1 e2 04             shl    $0x4,%rdx
  4b2d6c:       49 83 7c 14 18 00       cmpq   $0x0,0x18(%r12,%rdx,1)
  4b2d72:       74 e4                   je     4b2d58 <free_mem+0x258>
  4b2d74:       e9 cb fe ff ff          jmp    4b2c44 <free_mem+0x144>
  4b2d79:       e8 f2 be f7 ff          call   42ec70 <__free>
  4b2d7e:       49 c7 46 08 00 00 00    movq   $0x0,0x8(%r14)
  4b2d85:       00 
  4b2d86:       4d 8b 74 24 08          mov    0x8(%r12),%r14
  4b2d8b:       49 8b 0e                mov    (%r14),%rcx
  4b2d8e:       48 85 c9                test   %rcx,%rcx
  4b2d91:       74 9f                   je     4b2d32 <free_mem+0x232>
  4b2d93:       31 c0                   xor    %eax,%eax
  4b2d95:       eb 12                   jmp    4b2da9 <free_mem+0x2a9>
  4b2d97:       66 0f 1f 84 00 00 00    nopw   0x0(%rax,%rax,1)
  4b2d9e:       00 00 
  4b2da0:       48 83 c0 01             add    $0x1,%rax
  4b2da4:       48 39 c1                cmp    %rax,%rcx
  4b2da7:       74 89                   je     4b2d32 <free_mem+0x232>
  4b2da9:       48 89 c2                mov    %rax,%rdx
  4b2dac:       48 c1 e2 04             shl    $0x4,%rdx
  4b2db0:       49 83 7c 16 18 00       cmpq   $0x0,0x18(%r14,%rdx,1)
  4b2db6:       74 e8                   je     4b2da0 <free_mem+0x2a0>
  4b2db8:       e9 87 fe ff ff          jmp    4b2c44 <free_mem+0x144>
  4b2dbd:       48 8b 05 cc d3 02 00    mov    0x2d3cc(%rip),%rax        # 4e0190 <_dl_ns+0x10>
  4b2dc4:       8b 35 8e d3 02 00       mov    0x2d38e(%rip),%esi        # 4e0158 <_dl_initial_searchlist+0x8>
  4b2dca:       39 70 08                cmp    %esi,0x8(%rax)
  4b2dcd:       0f 85 e9 fd ff ff       jne    4b2bbc <free_mem+0xbc>
  4b2dd3:       48 8b 15 76 d3 02 00    mov    0x2d376(%rip),%rdx        # 4e0150 <_dl_initial_searchlist>
  4b2dda:       48 8b 38                mov    (%rax),%rdi
  4b2ddd:       48 89 10                mov    %rdx,(%rax)
  4b2de0:       c7 05 ae d3 02 00 00    movl   $0x0,0x2d3ae(%rip)        # 4e0198 <_dl_ns+0x18>
  4b2de7:       00 00 00 
  4b2dea:       e8 81 be f7 ff          call   42ec70 <__free>
  4b2def:       e9 c8 fd ff ff          jmp    4b2bbc <free_mem+0xbc>

Disassembly of section .fini:

00000000004b2df4 <_fini>:
  4b2df4:       f3 0f 1e fa             endbr64
  4b2df8:       48 83 ec 08             sub    $0x8,%rsp
  4b2dfc:       48 83 c4 08             add    $0x8,%rsp
  4b2e00:       c3                      ret
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx         
What's my favorite number? 18446744073709551615
Sorry, that's not it!
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 754635
picoCTF{up><_m3_f7w_77ad107e}
                                                                           
┌──(kali㉿kali)-[~/Downloads/unpackme]
└─$ 

```

## Referencias


