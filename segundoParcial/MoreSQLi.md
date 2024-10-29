# Retos picoCTF

# Level More SQLi

## Objetivo
Can you find the flag on this website.
Try to find the flag here.

## Solucion
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}
Primero ingreso con 'admin' y 'admin' para ver que pasa, al hacerno esto nos da una pista que podr`iamos usar **'or 1=1;--** para ingresar.

Efectivamente funciono.

123' UNION SELECT name, sql, null from sqlite_master;--

Ingresamos eso en el campo de texto para hacer una busqueda y nos dice que est`a la bandera, ahora usamos **123' UNION SELECT flag, null, null from more_table;--** para buscar la bandera.

## Referencias


