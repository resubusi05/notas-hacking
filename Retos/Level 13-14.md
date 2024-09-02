# Retos bandit

# Level 14

## Objetivo
Encontrar la contraseña está guardada en **/etc/bandit_pass/bandit14** y solo puede ser accedida por el usuario bandit14.

En este nivel no se va a obtener una contraseña, si no una llave SSH privada que puede ser usada para ingresar al siguiente nivel.

Nota: **localhost** es el hostname de la maquina en la que se está trabajando.

## Datos de acceso al nivel
Contraseña del nivel: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

## Solución
Contraseña bandit14: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS


Se entra al reto.

Buscamos **sshkey.private**.
![[Pasted image 20240831170404.png]]

Usamos la llave para acceder a bandit14 y buscar la contraseña de bandit14.![[Pasted image 20240831171123.png]]

Buscamos la contraseña.
![[Pasted image 20240831171539.png]]
![[Pasted image 20240831171601.png]]
![[Pasted image 20240831171645.png]]


## Notas

<!-- Comando para acceder al servidor usando la llave ssh: -->
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

**Es necesario "-i"**

## Referencias


