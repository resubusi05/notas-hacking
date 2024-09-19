# Retos picoCTF

# Level Repetitions 

## Objetivo
Can you make sense of this file? Download the file here.

## Solución

```
┌──(kali㉿kali)-[~/retosPico]
└─$ mkdir repetitions
                                                                        
┌──(kali㉿kali)-[~/retosPico]
└─$ cd repetitions 
                                                                        
┌──(kali㉿kali)-[~/retosPico/repetitions]
└─$ cat enc_flag  
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXMTRWMDVHV2toalJYUlhDazFyV25sVVZXaHpWakpHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
                                                                        
┌──(kali㉿kali)-[~/retosPico/repetitions]
└─$ strings enc_flag | grep pico
                                                                        
┌──(kali㉿kali)-[~/retosPico/repetitions]
└─$ base64 -d enc_flag
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JUVW14V05GWkhjRXRXCk1rWnlUVWhzVjJGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
                                                                        
┌──(kali㉿kali)-[~/retosPico/repetitions]
└─$ base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_4557ec3e}
                                                                        
┌──(kali㉿kali)-[~/retosPico/repetitions]
└─$ 

```

## Notas adicionales
El comando base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d decodifica un archivo o cadena codificada en base64 múltiples veces.

    base64 -d: decodifica datos en formato base64.
    enc_flag: es el archivo o texto codificado en base64 que se está procesando.
    Las tuberías (|) encadenan las decodificaciones para aplicar el proceso repetidamente.

En este caso, el archivo enc_flag se decodifica 6 veces consecutivas hasta revelar el contenido original. Cada ejecución toma el resultado de la anterior hasta llegar al dato fina 


## Referencias


