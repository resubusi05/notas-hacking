# Retos picoCTF

# Level Blame Game

## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

## Solución

```
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ git log flag.py
commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer
                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ git checkout feature/part-1
Switched to branch 'feature/part-1'
                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ cat flag.py                
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ git checkout feature/part-2
Switched to branch 'feature/part-2'
                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ cat flag.py                
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ git checkout feature/part-3
Switched to branch 'feature/part-3'
                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ cat flag.py                
print("Printing the flag...")

print("w0rk_798f9981}")
                                                                                                       
┌──(kali㉿kali)-[~/retosPico/collaborativeDevelopment/drop-in]
└─$ 
```


## Notas adicionales

## Referencias


