# Retos picoCTF

# Level Where are the robots

## Objetivo
Can you find the robots? https://jupiter.challenges.picoctf.org/problem/60915/ (link) or http://jupiter.challenges.picoctf.org:60915

## Solucion
Primero accedemos al link que se nos da, al final del link escribimos "robots.txt" y nos da lo siguiennte:
```
User-agent: *
Disallow: /8028f.html
```
Al final del link agregams la pagina para ver que nos da

```
Guess you found the robots
picoCTF{ca1cu1at1ng_Mach1n3s_8028f}
```

y encontramos la bandera

## Notas
robots.txt es un archivo de texto simple que se coloca en la raíz de un sitio web para dar instrucciones a los rastreadores web (también conocidos como "bots" o "web crawlers").


