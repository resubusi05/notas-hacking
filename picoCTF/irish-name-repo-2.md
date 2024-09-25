# Retos picoCTF

# Level Irish-Name-Repo 2

## Objetivo
There is a website running at https://jupiter.challenges.picoctf.org/problem/53751/ (link). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751

## Solucion
Al ingresar la inyeccion del reto pasado nos da el mensaje *SQLi detected.* 

Eso es una traba para las inyecciones SQL pero si ingresamos **admin'--**

"The -- is an SQL comment, and comments out the rest of the SQL such that it never checks if the password is correct. Enter the input in, and get your flag!"

## Referencias
https://nightxade.github.io/ctf-writeups/writeups/1337/picoCTF/web-exploitation/irish-name-repo-2.html


