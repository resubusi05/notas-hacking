# Retos picoCTF

# Level Mind your Ps and Qs

## Objetivo
In RSA, a small e value can be problematic, but what about N? Can you decrypt this? values
## Solucion
Para este reto opté por utilizar una herramienta en linea para la desencriptacion de la bandera.

´´´
┌──(kali㉿kali)-[~/Downloads/MindyourPsandQs]
└─$ ls             
values
                                                                               
┌──(kali㉿kali)-[~/Downloads/MindyourPsandQs]
└─$ file values    
values: ASCII text
                                                                               
┌──(kali㉿kali)-[~/Downloads/MindyourPsandQs]
└─$ cat values         
Decrypt my super sick RSA:
c: 861270243527190895777142537838333832920579264010533029282104230006461420086153423
n: 1311097532562595991877980619849724606784164430105441327897358800116889057763413423
e: 65537 
´´´

## Referencias
https://www.dcode.fr/rsa-cipher

