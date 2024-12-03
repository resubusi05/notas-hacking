# Retos picoCTF

# Level MSB

## Objetivo
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...
Download the image here
## Solucion
Para este reto usé un tutorial que vi en internet; https://github.com/snwau/picoCTF-2023-Writeup/blob/main/Forensics/MSB/MSB.md

en el tutorial se habla de una herramienta para poder extraer datos de MSB.

Los comando para usar esa herramienta son los siguientes
´´´
$ pip install Pillow
$ wget https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py

$ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
´´´

Despues de eso usamos grep para buscar la bandera en el resultado
´´´
                                                     
┌──(kali㉿kali)-[~/Downloads/MSB]
└─$ cat outputSB.txt | grep -o -E "picoCTF.{0,50}"
picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_b5e03bc5}"Thou h
              
´´´

## Referencias


