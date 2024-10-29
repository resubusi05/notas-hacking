# Retos picoCTF

# Level Search source

## Objetivo
The developer of this website mistakenly left an important artifact in the website source, can you find it?
The website is here

## Solucion

```
┌──(kali㉿kali)-[~/Downloads/segundoParcial]
└─$ wget -mpEk http://saturn.picoctf.net:62453/
--2024-10-27 23:37:34--  http://saturn.picoctf.net:62453/
Resolving saturn.picoctf.net (saturn.picoctf.net)... 13.59.203.175
Connecting to saturn.picoctf.net (saturn.picoctf.net)|13.59.203.175|:62453... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15920 (16K) [text/html]
Saving to: ‘saturn.picoctf.n

┌──(kali㉿kali)-[~/Downloads/segundoParcial]
└─$ grep -r 'picoCTF{'   
saturn.picoctf.net:62453/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/

```

## Referencias


