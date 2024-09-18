# Retos bandit

# Level 20

## Objetivo

Hay un setuid binario en home que hace lo siguiente: hace conexión a localhost en el puerto que se le especifique como argumento. Luego lee texto desde la conexión y lo compara con la contraseña del siguiente nivel(bandit 20). Si la contraseña es correcta, va a transmitir la contraseña del siguiente nivel.

Nota: Tratar de conectar tu propia network daemon para ver si funciona como lo esperarías.

## Datos de acceso al nivel
Contraseña del nivel: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

## Solución

Contraseña **bandit21**:  EeoULMCra2q0dSkYj561DX7s1CpBuOBt

```
PS C:\Users\vitoe> ssh bandit20@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit20@bandit.labs.overthewire.org's password:

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit20@bandit:~$ nc -lnvp 2020 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO &
[1] 2142187
bandit20@bandit:~$ Listening on 0.0.0.0 2020

bandit20@bandit:~$
bandit20@bandit:~$ ./sudoconnect 2020
-bash: ./sudoconnect: No such file or directory
bandit20@bandit:~$ ./suconnect 2020
Connection received on 127.0.0.1 48196
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
[1]+  Done                    nc -lnvp 2020 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
bandit20@bandit:~$

``` 
## Notas

Descripción del comando `nc -lnvp 2020 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO & `:
### 1. `nc`

Este es el comando **Netcat**, una herramienta de red que se utiliza para leer y escribir en conexiones de red utilizando el protocolo TCP o UDP. Netcat se puede usar para diversas tareas, como establecer conexiones de red, transferir archivos, escanear puertos, etc.

### 2. `-l`

Esta opción indica que **Netcat** actuará como servidor o listener, es decir, estará "escuchando" en un puerto específico para una conexión entrante.

### 3. `-n`

Esta opción le indica a **Netcat** que no intente hacer un DNS lookup o una búsqueda de nombres de host; solo se utilizan direcciones IP numéricas.

### 4. `-v`

La opción **verbose**, que significa que el comando mostrará información más detallada de lo que está ocurriendo.

### 5. `-p 2020`

Esto especifica el puerto en el que **Netcat** estará escuchando. En este caso, será el puerto **2020**.

### 6. `<<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`

Este es un operador **Here-string**, que envía la cadena `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO` como entrada estándar al comando. Esto significa que el comando **Netcat** recibirá esta cadena de texto como si fuera una entrada desde el teclado o desde un archivo.

### 7. `&`

Este símbolo al final del comando es para ejecutarlo en **segundo plano**. Esto significa que el comando seguirá ejecutándose, pero no bloqueará el uso de la terminal para otras tareas.

## Referencias


