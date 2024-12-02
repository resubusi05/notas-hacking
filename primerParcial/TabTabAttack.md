# Retos picoCTF

# Level Tab, Tab, Attack

## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: Addadshashanammu.zip

## Solución
```
┌──(kali㉿kali)-[~/Downloads/TabTabAttack]
└─$ ls
Addadshashanammu  Addadshashanammu.zip
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/TabTabAttack]
└─$ cd Addadshashanammu 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/TabTabAttack/Addadshashanammu]
└─$ cd Almurbalarammi  
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/TabTabAttack/Addadshashanammu/Almurbalarammi]
└─$ cd Ashalmimilkala 
                                                                                                   
┌──(kali㉿kali)-[~/…/TabTabAttack/Addadshashanammu/Almurbalarammi/Ashalmimilkala]
└─$ cd Assurnabitashpi 
                                                                                                   
┌──(kali㉿kali)-[~/…/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi]
└─$ cd Maelkashishi   
                                                                                                   
┌──(kali㉿kali)-[~/…/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi]
└─$ cd Onnissiralis 
                                                                                                   
┌──(kali㉿kali)-[~/…/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis]
└─$ cd Ularradallaku 
                                                                                                   
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls                   
fang-of-haynekhtnamet
                                                                                                   
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=e34ce4e4ee2f7ce7fb251c8f5ab036da9882bc55, not stripped
                                                                                                   
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}

```
## Notas adicionales

## Referencias


