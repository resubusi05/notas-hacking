# Retos picoCTF

# Level It is my Birthday

## Objetivo
I sent out 2 invitations to all of my friends for my birthday! I'll know if they get stolen because the two invites look similar, and they even have the same md5 hash, but they are slightly different! You wouldn't believe how long it took me to find a collision. Anyway, see if you're invited by submitting 2 PDFs to my website. http://mercury.picoctf.net:63578/
## Solucion
En este reto, nos pide que enviemos dos pdf distintos, ambos usan md5 hash por lo que al buscar MD5 en internet, me encontré con la siguiente pagina: https://www.mscs.dal.ca/~selinger/md5collision/

De aquí desacrgue ambos archivos(para linux) y simplemente los odifiqué para que su extension fuese .pdf.

Los subí a la pagina, y ahí estaba la bandera

'''
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ wget https://www.mscs.dal.ca/~selinger/md5collision/hello
--2024-12-02 21:45:32--  https://www.mscs.dal.ca/~selinger/md5collision/hello
Resolving www.mscs.dal.ca (www.mscs.dal.ca)... 129.173.118.86
Connecting to www.mscs.dal.ca (www.mscs.dal.ca)|129.173.118.86|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4072 (4.0K)
Saving to: ‘hello’

hello              100%[===============>]   3.98K  --.-KB/s    in 0s      

2024-12-02 21:45:33 (104 MB/s) - ‘hello’ saved [4072/4072]

                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ ls
hello
                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ cp hello  hello.pdf              
                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ ls
hello  hello.pdf
                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ wget https://www.mscs.dal.ca/~selinger/md5collision/erase
--2024-12-02 21:46:10--  https://www.mscs.dal.ca/~selinger/md5collision/erase
Resolving www.mscs.dal.ca (www.mscs.dal.ca)... 129.173.118.86
Connecting to www.mscs.dal.ca (www.mscs.dal.ca)|129.173.118.86|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4072 (4.0K)
Saving to: ‘erase’

erase              100%[===============>]   3.98K  --.-KB/s    in 0s      

2024-12-02 21:46:10 (123 MB/s) - ‘erase’ saved [4072/4072]

                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ ls                                                       
erase  hello  hello.pdf
                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$ cp erase erase.pdf 
                                                                           
┌──(kali㉿kali)-[~/Downloads/ItismyBirthday]
└─$           
'''

## Referencias


