# Retos bandit

# Level 8

## Objetivo
Es encontrar la contraseña que esta en el archivo data.txt junto a la palabra "millionth"
## Datos de acceso al nivel

Contraseña del nivel: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj


## Solución

Contraseña: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Se accede al juego.

Uso el comendo "ls -la" para ver los archivos del directorio.

Veo data.txt, al abrirlo con cat se abre una lista de una cantidad enorme de palabras aleatorias junto a cadenas de texto, haciendo que encontrar la palabra fuese extremadamente difícil.

Utilizo el comando "grep -E "millionth.*" data.txt"  para buscar palabras que esten junto a la palabra "millionth" y me da la palabra junto a la contraseña.
![[Pasted image 20240828020213.png]]



## Notas

Explicación del comando grep -E "millionth.*" data.txt

Esta expresión busca cualquier línea que contenga `palabra1` seguida de cualquier cosa (o nada).

## Referencias


