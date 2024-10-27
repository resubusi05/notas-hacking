# Retos picoCTF

# Level Pixelates

## Objetivo
I have these 2 images, can you make a flag out of them? scrambled1.png scrambled2.png

## Solucion
```
┌──(kali㉿kali)-[~/Downloads/pixelated]
└─$ convert scrambled1.png scrambled2.png -ompose Add -composite bandera.png  
convert-im6.q16: unrecognized option `-ompose' @ error/convert.c/ConvertImageCommand/2290.
                                                                    
┌──(kali㉿kali)-[~/Downloads/pixelated]
└─$ ls
scrambled1.png  scrambled2.png  solved.bmp
                                                                    
┌──(kali㉿kali)-[~/Downloads/pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite bandera.png
                                                                    
┌──(kali㉿kali)-[~/Downloads/pixelated]
└─$ ls
bandera.png  scrambled1.png  scrambled2.png  solved.bmp
                                                                    
┌──(kali㉿kali)-[~/Downloads/pixelated]
└─$ open bandera.png 
```
picoCTF{2a4d45c7}


## Referencias


