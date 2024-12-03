# Retos picoCTF

# Level shark on wire 1

## Objetivo
We found this packet capture. Recover the flag.

## Solucion
picoCTF{StaT31355_636f6e6e}

Para esto, usamos wireshark, deontro de wirechark le di click a un paquete UPD, vemos que lo que contiene es solo un caracter. En ese caso l mismo paquete UDP se le da click derecho y en "follow", despues "follow UDP stream", al hacer esto nos da una cadena que parece aleatoria pero navegando en los distintos streams nos topamos con la bandera.

## Referencias


