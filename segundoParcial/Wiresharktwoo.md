# Retos picoCTF

# Level Wireshark twoo

## Objetivo
Can you find the flag? shark2.pcapng.
## Solucion
ESte reto fue algo complicado de entender, al principio con ayuda de la busqueda encontre lo que pensaba que era la banera, pero al indagar un pco más me dicuenta que había varias "banderas" falsas por lo que no era lo que estaba buscando. Pero estas banderas tenian algo en común; todas hacen referencia unapagina ccon el ip 192.168.38.104 así que se aplico un filtro para que me mostrase los paquetes de esta direccion, al indagar un poco más encontré que habia una cadena en lo que parece ser base64, así que junté toda la cadena y la decodifiqué, dandome así la bandera.

picoCTF{dns_3xf1l_ftw_deadbeef}

## Referencias


