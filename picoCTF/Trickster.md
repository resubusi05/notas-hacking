# Retos picoCTF

# Level Trickster

## Objetivo
I found a web app that can help process images: PNG images only!
Try it here!
## Solucion
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_48785c0e}

Para este reto, usamos un webshell, primero copeamos el web sehhl a la carpeta donde me encuentro, despues de eso, me doy cuenta que la pagina si verifica que los magic bytes y la extencion del archivo que se suba, si sea .png por lo que se modigica el archivo .php para que coincida.

Despues subimos el archivo a la pagina y usamos ffuf para buscar donde se guardó el archivo, una vez encontrado el directorio, una vez en el directorio, tenemos control de el servidor donde esta y buscamos la bandera

este comendo nos ayuda a encontrar todos los archivos con terminación .php 
find / -name *txt 2>/dev/null

'''
┌──(kali㉿kali)-[~]
└─$ cd Downloads 
                                                                                                                                                                     
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Trikster 
                                                                                                                                                                     
┌──(kali㉿kali)-[~/Downloads/Trikster]
└─$ ls                               
webshell.php  webshell.png.php
                                                                                                                                                                     
┌──(kali㉿kali)-[~/Downloads/Trikster]
└─$ ffuf -u http://atlas.picoctf.net:62423/ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt -ic  

Keyword FUZZ defined, but not found in headers, method, URL or POST data.

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.1.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://atlas.picoctf.net:62423/
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,500
________________________________________________

                        [Status: 200, Size: 321, Words: 53, Lines: 17, Duration: 206ms]
:: Progress: [1/1] :: Job [1/1] :: 0 req/sec :: Duration: [0:00:00] :: Errors: 0 ::
                                                                                                                                                                     
┌──(kali㉿kali)-[~/Downloads/Trikster]
└─$ ffuf -u http://atlas.picoctf.net:62423/ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt -ic 

Keyword FUZZ defined, but not found in headers, method, URL or POST data.

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.1.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://atlas.picoctf.net:62423/
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,500
________________________________________________

                        [Status: 200, Size: 321, Words: 53, Lines: 17, Duration: 208ms]
:: Progress: [1/1] :: Job [1/1] :: 0 req/sec :: Duration: [0:00:00] :: Errors: 0 ::
                                                                                                     
┌──(kali㉿kali)-[~/Downloads/Trikster]
└─$ ffuf -u http://atlas.picoctf.net:62423/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt -ic


        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.1.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://atlas.picoctf.net:62423/FUZZ
 :: Wordlist         : FUZZ: /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,5
________________________________________________

                        [Status: 200, Size: 321, Words: 53, Lines: 17, Du
uploads                 [Status: 301, Size: 333, Words: 20, Lines: 10, Du
[WARN] Caught keyboard interrupt (Ctrl-C)
                                                                         


'''

## Referencias


