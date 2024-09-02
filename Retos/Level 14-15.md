# Retos bandit

# Level 14

## Objetivo

La contraseña puede puede ser llamada ingresando la contraseña de este nivel al puerto 30000 en localhost

## Datos de acceso al nivel
Contraseña del nivel: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

## Solución

Contraseña **bandit15**:  8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

Se accede al nivel.

Ingreso el siguiente comando para enviar la contraseña al puerto indicado; echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000.
![[Pasted image 20240831175438.png]]

## Notas
Descripción del comando "echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000"
	

- **`echo "<tu_contraseña_actual>"`**:
    
    - Este comando imprime (`echo`) la cadena `<tu_contraseña_actual>` en la consola.
- **`|`** (pipe):
    
    - Este símbolo toma la salida del comando a la izquierda (en este caso, la salida de `echo`) y la pasa como entrada al comando a la derecha.
- **`nc localhost 30000`**:
    
    - `nc` es una abreviatura de `netcat`, una herramienta que puede leer y escribir datos a través de conexiones de red utilizando los protocolos TCP o UDP.
    - `localhost` indica que la conexión se hará a la máquina local (la misma en la que se está ejecutando el comando).
    - `30000` es el puerto en el que `nc` intentará conectarse en `localhost`.
## Referencias


