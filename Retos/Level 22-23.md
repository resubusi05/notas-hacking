# Retos bandit

# Level 22

## Objetivo

Un programa se ejecuta automaticamente en intervalos regulares desde cron. Ve en /etc/cron.d para la configuración y ve cual comando esta siendo ejecutado.

## Datos de acceso al nivel
Contraseña del nivel: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

## Solución

Contraseña **bandit23**:  0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

```
bandit22@bandit:~$ cd /etc/cron.d
bandit22@bandit:/etc/cron.d$ ls -la
total 44
drwxr-xr-x   2 root root  4096 Jul 17 15:59 .
drwxr-xr-x 121 root root 12288 Aug  1 14:49 ..
-rw-r--r--   1 root root   120 Jul 17 15:57 cronjob_bandit22
-rw-r--r--   1 root root   122 Jul 17 15:57 cronjob_bandit23
-rw-r--r--   1 root root   120 Jul 17 15:57 cronjob_bandit24
-rw-r--r--   1 root root   201 Apr  8 14:38 e2scrub_all
-rwx------   1 root root    52 Jul 17 15:59 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 31 00:06 .placeholder
-rw-r--r--   1 root root   396 Jan  9  2024 sysstat
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:/etc/cron.d$ whoami
bandit22
bandit22@bandit:/etc/cron.d$ myname=bandit23
bandit22@bandit:/etc/cron.d$ echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:/etc/cron.d$
bandit22@bandit:/etc/cron.d$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

```
## Notas

Descripción del comando **echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)**

- **`echo I am user $myname`**:
    
    - Este es un comando `echo` que imprime el texto `I am user $myname`.
    - Si tienes definida una variable de entorno llamada `$myname`, ésta será reemplazada por su valor.
    - Por ejemplo, si `$myname` es "John", entonces el comando se convierte en `echo I am user John`.
- **`| md5sum`**:
    
    - El símbolo `|` se llama "pipe" y toma la salida del comando anterior (`echo I am user $myname`) y la pasa como entrada al siguiente comando.
    - `md5sum` genera un "hash" MD5 de la cadena de texto que recibe.
    - Por ejemplo, la salida de `echo I am user John` se pasaría a `md5sum`, que generaría el hash correspondiente a esa cadena.
- **`| cut -d ' ' -f 1`**:
    
    - El comando `cut` se utiliza para seleccionar partes específicas de una cadena de texto.
    - `-d ' '` indica que el delimitador (separador) es un espacio en blanco.
    - `-f 1` significa que se tomará solo la primera parte de la cadena dividida por espacios.
    - `md5sum` genera un hash seguido de un espacio y un guion, y con este comando seleccionas solo el hash.
- **`echo $(...)`**:
    
    - La parte `$(...)` ejecuta lo que está dentro de los paréntesis y usa la salida como si fuera parte del comando `echo`.
    - En este caso, la salida será el hash MD5.


## Referencias


