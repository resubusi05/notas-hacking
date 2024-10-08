# Retos picoCTF

# Level m00nwalk

## Objetivo
Decode this message from the moon.
## Solucion
Se utilizo el repositorio https://github.com/colaclanth/sstv que proporciona una herramienta para decodificar el audio y nos da una imagen que nos da la bandera

```
┌──(kali㉿kali)-[~/Downloads]
└─$ sstv -d message.wav -o bandera.jpg
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [############################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ open bandera.jpg
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ 

``` 
 
picoCTF{beep_boop_im_in_space}

## Referencias


