# Retos picoCTF

# Level St3g0

## Objetivo
Download this image and find the flag.
Download image
## Solucion
Para este progama tuve que encontrar una herramienta que me permitiese ver la info de la imagen.
´´´
┌──(kali㉿kali)-[~/Downloads/St3g0]
└─$ ls
pico.flag.png
                                                                          
┌──(kali㉿kali)-[~/Downloads/St3g0]
└─$ open pico.flag.png
                                                                          
┌──(kali㉿kali)-[~/Downloads/St3g0]
└─$ zsteg pico.flag.png
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a1062667}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
                
´´´

## Referencias
https://book.hacktricks.xyz/crypto-and-stego/stego-tricks

