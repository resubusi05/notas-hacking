# Retos picoCTF

# Level rotation

## Objetivo
You will find the flag after decrypting this file
Download the encrypted flag here.

## Solucion
picoCTF{r0tat1on_d3crypt3d_555957f3}

Con cyberchef, simplemente se ingreso el texto de la bandera y se le aplico un rot18

```
┌──(kali㉿kali)-[~/Downloads]
└─$ mkdir rotation 
                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ cd rotation 
                                                                                                            
┌──(kali㉿kali)-[~/Downloads/rotation]
└─$ wget https://artifacts.picoctf.net/c/385/encrypted.txt
--2024-11-23 15:58:03--  https://artifacts.picoctf.net/c/385/encrypted.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 37 [application/octet-stream]
Saving to: ‘encrypted.txt’

encrypted.txt              100%[========================================>]      37  --.-KB/s    in 

2024-11-23 15:58:04 (83.8 MB/s) - ‘encrypted.txt’ saved [37/37]

                                                                                                   
┌──(kali㉿kali)-[~/Downloads/rotation]
└─$ cat encrypted.txt 
xqkwKBN{z0bib1wv_l3kzgxb3l_555957n3}
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/rotation]
└─$ 
```

## Referencias


