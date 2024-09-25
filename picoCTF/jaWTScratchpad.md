# Retos picoCTF

# Level JaWT Scratchpad

## Objetivo
Check the admin scratchpad! https://jupiter.challenges.picoctf.org/problem/58210/ or http://jupiter.challenges.picoctf.org:58210

## Solucion

Se imgresa a la pagina, se inspeccionan las cookies y encontramos una con un
token JWT. Para encontrar la palabra de seguridad usamos **JohnTheRipper**

```
┌──(kali㉿kali)-[~]
└─$ john jwt --format=HMAC-SHA256 --wordlist=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 6 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:00 DONE (2024-09-24 23:53) 1.111g/s 8219Kp/s 8219Kc/s 8219KC/s iloveyokaos..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

```

## Referencias


