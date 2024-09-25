# Retos picoCTF

# Level Irish-Name-Repo 1

## Objetivo
There is a website running at https://jupiter.challenges.picoctf.org/problem/50009/ (link) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Solucion
Se ingresa a la pagina, y se trata de hacer login, se obserav que se envia un POST con el siguiente dato debug	"0" eso nos c¿dice que una inyeccion sql puede servir.

' OR '1'='1' -- 

picoCTF{s0m3_SQL_fb3fe2ad}

## Referencias

