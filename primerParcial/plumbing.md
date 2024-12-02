# Retos picoCTF

# Level plumbing

## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to jupiter.challenges.picoctf.org 7480.

## Solución
```                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 7480
Not a flag either
Not a flag either
Not a flag either
Not a flag either
Not a flag either

```

```
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 7480 | grep picoCTF
picoCTF{digital_plumb3r_06e9d954}

```
## Notas adicionales

## Referencias


