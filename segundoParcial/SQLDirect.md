# Retos picoCTF

# Level SQL Direct

## Objetivo
Connect to this PostgreSQL server and find the flag!
psql -h saturn.picoctf.net -p 52014 -U postgres pico
Password is postgres

## Solucion
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

```
┌──(kali㉿kali)-[~/Downloads/segundoParcial]
└─$ psql -h saturn.picoctf.net -p 59949 -U postgres pico

Password for user postgres: 
psql (16.1 (Debian 16.1-1+b1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# Select * from flags;

zsh: suspended  psql -h saturn.picoctf.net -p 59949 -U postgres pico
```
Al hacer esto se conecta con el SQL y bucamo las banderas y nos arroja la que buscamos.

## Referencias


