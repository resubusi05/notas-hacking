# Retos picoCTF

# Level Java Code Analysis

## Objetivo
BookShelf Pico, my premium online book-reading service.
I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!
Here are the credentials to get you started:
Username: "user"
Password: "user"
Source code can be downloaded here.
Website can be accessed here!.
## Solucion
Para este problema, primero analice un poco el codigo de JAva con esto me di cuenta de varias cosas, primero que no se va a desvloquear el libro Flag sin no tengo como role Admin, el userId 2 y el email admin.

Despues al ver la pagina con BurpSuite encontre el token JWT, lo modifiqué y lo cargué nuevamente en la pagina, dandome la bandera

## Referencias
https://jwt.io/
