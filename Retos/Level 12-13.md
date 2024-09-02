# Retos bandit

# Level 13
	x
## Objetivo
Encontrar la contraseña en el data.txt, es un hexdump de un archivo que ha sido comprimido varias veces,  se puede crear un directorio dentro de /tmp en que podré trabajar.

Usar el comando "mktemp -d", copiar el  archivo usando cp y renombrarlo usando mv (leer manpages!).
## Datos de acceso al nivel
Contraseña del nivel: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

## Solución
Contraseña **bandit13**: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

Se inicia sesión en el juego.
Ingreso a tmp y creo el directorio temporal donde trabajar y  busco el archivo data.txt y lo mando a tmp.
![[Pasted image 20240829234551.png]]
![[Pasted image 20240829234625.png]]

Descomprimo el archivo una vez, y comienzo con el proceso de descomprimir  ![[Pasted image 20240829234724.png]]

Y así hasta dar con la contraseña.
![[Pasted image 20240829234804.png]]

## Notas
Descripción de los comandos usados:

- **`xxd -r data.txt data.bin`**:
    
    - Convierte un archivo en formato hexdump de vuelta a su formato binario original.
- **`file data.bin`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data.bin`.
- **`mv data.bin data.gz`**:
    
    - Cambia el nombre del archivo `data.bin` a `data.gz`.
- **`gzip -d data.gz`**:
    
    - Descomprime un archivo `gzip`, creando el archivo descomprimido.
- **`ls`**:
    
    - Lista los archivos y directorios en el directorio actual.
- **`cat data`**:
    
    - Muestra el contenido del archivo `data` en la terminal.
- **`file data`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data`.
- **`mv data data.bz2`**:
    
    - Cambia el nombre del archivo `data` a `data.bz2`.
- **`bzip2 -s data.bz2`**:
    
    - Intenta mostrar el tamaño comprimido del archivo `data.bz2`. No se ejecuta correctamente porque el archivo ya tiene la extensión `.bz2`.
- **`bzip2 -d data.bz2`**:
    
    - Descomprime un archivo comprimido con `bzip2`.
- **`file data`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data` (luego de la descompresión).
- **`mv data data.gz`**:
    
    - Cambia el nombre del archivo `data` a `data.gz`.
- **`gzip -d data.gz`**:
    
    - Descomprime un archivo `gzip`.
- **`file data`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data` (luego de la descompresión).
- **`tar -xf data`**:
    
    - Extrae el contenido de un archivo tar.
- **`mv data5.bin data.z`**:
    
    - Cambia el nombre del archivo `data5.bin` a `data.z`.
- **`mv data.z data5.bin`**:
    
    - Cambia el nombre del archivo `data.z` a `data5.bin`.
- **`file data5.gz`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data5.gz`.
- **`tar -xzf data.gz`**:
    
    - Intenta extraer un archivo tar comprimido con gzip. Falla porque el archivo no existe.
- **`tar -xf data5.gz`**:
    
    - Extrae el contenido de un archivo tar.
- **`file data6.bin`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data6.bin`.
- **`mv data6.bin data6.bz2`**:
    
    - Cambia el nombre del archivo `data6.bin` a `data6.bz2`.
- **`bzip -d data.bz2`**:
    
    - Intenta descomprimir un archivo con `bzip`, pero no encuentra el archivo porque no existe.
- **`bzip2 -d data6.bz2`**:
    
    - Descomprime un archivo `bzip2`.
- **`cat data6`**:
    
    - Muestra el contenido del archivo `data6`.
- **`file data6`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data6`.
- **`tar -xf data6`**:
    
    - Extrae el contenido de un archivo tar.
- **`la -la`**:
    
    - Error tipográfico del comando `ls -la` que debería listar archivos con detalles.
- **`file data8.bin`**:
    
    - Muestra el tipo de archivo y detalles sobre el contenido de `data8.bin`.
- **`mv data8.bin data8.gz`**:
    
    - Cambia el nombre del archivo `data8.bin` a `data8.gz`.
- **`gzip -d data8.gz`**:
    
    - Descomprime un archivo `gzip`.


## Referencias


