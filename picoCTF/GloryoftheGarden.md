# Retos picoCTF

# Level Glory of the Garden

## Objetivo
This garden contains more than it seems.

## Solucion
picoCTF{more_than_m33ts_the_3y3657BaB2C}

Para este programa se descarga la imagen y se usa hexeditor para ver el codigo, en hexeditor, busco la cadena "picoCTF" y encontramos en el final la bandera

'''
┌──(kali㉿kali)-[~/Downloads/GloryoftheGarden]
└─$ open garden.jpg 
                                                                                  
┌──(kali㉿kali)-[~/Downloads/GloryoftheGarden]
└─$ file garden.jpg 
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
                                                                                  
┌──(kali㉿kali)-[~/Downloads/GloryoftheGarden]
└─$ grep 'picoCTF' file garden.jpg 
grep: file: No such file or directory
grep: garden.jpg: binary file matches
                                                                                  
┌──(kali㉿kali)-[~/Downloads/GloryoftheGarden]
└─$ hexeditor garden.jpg  
                                                                                  
┌──(kali㉿kali)-[~/Downloads/GloryoftheGarden]
└─$ 

'''

## Referencias


