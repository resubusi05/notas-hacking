# Retos picoCTF

# Level Eavesdrop

## Objetivo
Download this packet capture and find the flag.
Download packet capture
## Solucion
Analizando el archivo que se nos dió, podemos encontrar una conversasion:
***
Hey, how do you decrypt this file again?
You're serious?
Yeah, I'm serious
*sigh* openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
Ok, great, thanks.
Let's use Discord next time, it's more secure.
C'mon, no one knows we use this program like this!
Whatever.
Hey.
Yeah?
Could you transfer the file to me again?
Oh great. Ok, over 9002?
Yeah, listening.
Sent it
Got it.
You're unbelievable
***

Esto nos da como pista que puede haber un archivo llamado file.des3

Encuentro el archivo en el puerto 9002, así que guardo el archivo y lo desencripto usando el comando de la conversación.

´´´
┌──(kali㉿kali)-[~/Downloads/Eavesdrop]
└─$ openssl des3 -d -salt -in file.3des -out file.txt -k supersecretpassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                             
┌──(kali㉿kali)-[~/Downloads/Eavesdrop]
└─$ ls
capture.flag.pcap  file.3des  file.txt
                                                             
┌──(kali㉿kali)-[~/Downloads/Eavesdrop]
└─$ cat file.       
cat: file.: No such file or directory
                                                             
┌──(kali㉿kali)-[~/Downloads/Eavesdrop]
└─$ cat file.txt
picoCTF{nc_73115_411_5786acc3}                                                             
┌──(kali㉿kali)-[~/Downloads/Eavesdrop]
└─$ 

´´´

## Referencias


