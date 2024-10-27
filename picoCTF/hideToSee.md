# Retos picoCTF

# Level HideToSee

## Objetivo
How about some hide and seek heh? Look at this image here.

## Solucion
picoCTF{atbash_crack_1f84d779}

```
┌──(kali㉿kali)-[~/Downloads/hideToSee]
└─$ ls
atbash.jpg
                                                                    
┌──(kali㉿kali)-[~/Downloads/hideToSee]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                    
┌──(kali㉿kali)-[~/Downloads/hideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_1u84w779}
                                                                    
┌──(kali㉿kali)-[~/Downloads/hideToSee]
└─$ 

```

## Referencias


