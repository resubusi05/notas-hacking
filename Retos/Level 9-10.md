# Retos bandit

# Level 10

## Objetivo
Encontrar la contraseña en el data.txt, tiene que ser human-readable y estar seguida de muchos "="
## Datos de acceso al nivel

Contraseña del nivel: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
## Solución

Contraseña bandit10: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Se accede al nivel.

Localizo el archivo data.txt usando "ls -la"
![[Pasted image 20240829200101.png]]

Ingreso el siguiente comando (grep -a -o -E '={2,}\s*\S+' data.txt) para buscar la contraseña.
![[Pasted image 20240829200133.png]]
## Notas

Explicación del comando "grep -a -o -E '={2,}\s*\S+' data.txt"
	`-o`: Muestra solo las partes de las líneas que coinciden con el patrón.
- `-E`: Activa las expresiones regulares extendidas.
- `'{2,}'`: Busca dos o más signos "=".
- `\s*`: Permite que haya espacios en blanco después de los signos "=".
- `\S+`: Busca cualquier secuencia de caracteres que no sea un espacio (lo que capturará la palabra o texto junto a los signos "=").
- `nombre_del_archivo`: Es el nombre del archivo en el que estás buscando.
- `-a` o `--text`: Forza a `grep` a tratar el archivo como un archivo de texto, incluso si contiene caracteres no imprimibles.
## Referencias


