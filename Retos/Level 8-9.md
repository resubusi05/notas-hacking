# Retos bandit

# Level 9

## Objetivo
Encontrar la contraseña en el data.txt y tiene que ser la única linea que se repita una sola vez
## Datos de acceso al nivel

Contraseña del nivel: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
## Solución

Contraseña bandit9: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

Se accede al nivel.
Se usa "ls -la" y veo que el archivo data.txt es muy grande.

Uso el comando "sort data.txt | uniq -u" y encuentro la contraseña.
![[Pasted image 20240828020951.png]]

## Notas

Explicación del comando "sort data.txt | uniq -u"
	Este comando primero ordena el archivo y luego usa `uniq -u` para mostrar solo las líneas que aparecen una vez en el archivo.
## Referencias


