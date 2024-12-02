# Retos picoCTF

# Level Glitch Cat

## Objetivo
Our flag printing service has started glitching!
$ nc saturn.picoctf.net 53252

## Solución
picoCTF{gl17ch_m3_n07_9c42a45d}

```
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/GlitchCat]
└─$ nc saturn.picoctf.net 53252        
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/GlitchCat]
└─$ python3         
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x39)
'9'
>>> chr(0x63)
'c'
>>> chr(0x34)
'4'
>>> chr(0x32)
'2'
>>> chr(0x61)
'a'
>>> chr(0x34)
'4'
>>> chr(0x35)
'5'
>>> chr(0x64)
'd'

```

## Notas adicionales

## Referencias


