# Retos bandit

# Level 15

## Objetivo

La contraseña del siguiente nivel puede ser obtenida enviando la contraseña al puerto **30001** en **localhost** haciendo uso de la encriptación SSL/TLS

Nota: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.
## Datos de acceso al nivel
Contraseña del nivel: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

## Solución

Contraseña **bandit16**:  kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

Ingresamos al nivel.
conectamos con el puerto 30001 usando el siguiente comando: openssl s_client -connect localhost:30001
![[Pasted image 20240901220313.png]]

Ingresamos la contraseña  de este nivel y nos da la del siguiente.
![[Pasted image 20240901220348.png]]


## Notas

Descripción del comando **openssl s_client -connect localhost:30001 :**
 
### `openssl`
 
- **Descripción**: `openssl` es una poderosa herramienta de línea de comandos utilizada para implementar las funciones del conjunto de herramientas OpenSSL. Este conjunto incluye una amplia variedad de funciones criptográficas, como la generación de claves, la creación de certificados, la verificación de certificados, el cifrado y descifrado de datos, y la gestión de conexiones seguras mediante SSL/TLS.

### `s_client`

- **Descripción**: Este subcomando de `openssl` actúa como un cliente SSL/TLS genérico. Se utiliza principalmente para probar y depurar conexiones seguras a servidores. Al ejecutar este subcomando, se establece una conexión segura al servidor especificado y se inicia una sesión de cliente SSL/TLS interactiva. Esto te permite ver detalles de la conexión y del certificado, además de enviar datos al servidor en formato encriptado.

### `-connect localhost:30001`

- **Descripción**: Este argumento especifica la dirección y el puerto al cual `openssl` intentará conectarse.
    - **localhost**: Esto indica que la conexión se realizará a la máquina local. Si se quisiera conectar a un servidor remoto, se reemplazaría `localhost` por el nombre de dominio o la dirección IP del servidor.
    - **30001**: Es el número de puerto en el que el servidor está escuchando para conexiones SSL/TLS.
## Referencias


