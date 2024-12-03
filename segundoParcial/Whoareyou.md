# Retos picoCTF

# Level Who are you??
## Objetivo
Let me in. Let me iiiiiiinnnnnnnnnnnnnnnnnnnn http://mercury.picoctf.net:34588/
cd 
## Solucion
Para poder solucionar este reto, hay que cambiar el header que se envia a la pagina para que nos de la bandera.

El header original:
GET / HTTP/1.1
Host: mercury.picoctf.net:34588
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: close
Upgrade-Insecure-Requests: 1|

El header modificado:
GET / HTTP/1.1
Host: mercury.picoctf.net:34588
User-Agent: PicoBrowser
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: close
Referer: http://mercury.picoctf.net:34588
Date: 18 Oct 2018
DNT: true
X-Forwarded-For: 103.103.84.25
Accept-Language: sv
Upgrade-Insecure-Requests: 1



## Referencias


