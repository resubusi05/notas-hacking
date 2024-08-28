# Retos bandit

# Level 7

## Objetivo
Es encontrar la contraseña que esta en algún lugar del server y tiene las siguientes propiedades:

- owned by bandit7
- owned by group bandit6
- 33 bytes.


## Datos de acceso al nivel

Contraseña del nivel: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG


## Solución

Contraseña:  morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

Se accede al reto.
![[Pasted image 20240828014215.png]]


Comenzamos a husmear en el servidor.
![[Pasted image 20240828014252.png]]
![[Pasted image 20240828014305.png]]

Veo que hay demasiados directorios, hago un comando para buscar un archivo con las caracteristicas dadas y que tenga permiso.
![[Pasted image 20240828014417.png]]

Vamos a la ruta del archivo y lo abrimos para obtener la contraseña.
![[Pasted image 20240828014615.png]]



## Notas adicionales

Explicación del comando para buscar el archivo:

find -type f -user bandit7 -group bandit6 -size 33c 2>/dev
/nullx

- `/home/bandit7`: Especifica el directorio desde el cual deseas comenzar la búsqueda. Puedes cambiar este valor si el archivo puede estar en otra ubicación.
- `-type f`: Busca solo archivos regulares (excluyendo directorios, enlaces simbólicos, etc.).
- `-user bandit7`: Filtra los archivos que son propiedad del usuario `bandit7`.
- `-group bandit6`: Filtra los archivos que pertenecen al grupo `bandit6`.
- `-size 33c`: Busca archivos que tengan un tamaño exacto de 33 bytes (`c` indica bytes).
- `2>/dev/null`: Redirige el flujo de errores estándar (stderr) a `/dev/null`, que es un "pozo" especial que descarta cualquier cosa que se le envíe. Esto significa que no verás los mensajes de "Permission denied" en la salida del comando.

## Referencias


