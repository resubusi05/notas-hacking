# Retos picoCTF

# Level Transformation

## Objetivo
I wonder what this really is... enc ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

## Solucion
picoCTF{16_bits_inst34d_of_8_04c0760d}
Con ayuda se cyber chef encontramos su codificado que es: Encode_text('UTF-16BE (1201)') 

```
┌──(kali㉿kali)-[~/Downloads/Transformation]
└─$ ls
enc
                                                                                                                      
┌──(kali㉿kali)-[~/Downloads/Transformation]
└─$ file enc        
enc: Unicode text, UTF-8 text, with no line terminators
                                                                                                                      
┌──(kali㉿kali)-[~/Downloads/Transformation]
└─$ cat enc           
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰㑣〷㘰摽                                                                                                                      

```

## Referencias


