# Retos picoCTF

# Level Super SSH 

## Objetivo
Using a Secure Shell (SSH) is going to be pretty important.

Additional details will be available after launching your challenge instance.

## Solución

```
┌──(kali㉿kali)-[~/retosPico]
└─$ mkdir superSSH   
                                                                        
┌──(kali㉿kali)-[~/retosPico]
└─$ cd superSSH 
                                                                        
┌──(kali㉿kali)-[~/retosPico/superSSH]
└─$ ssh -p 64296 ctf-player@titan.picoctf.net
The authenticity of host '[titan.picoctf.net]:64296 ([3.139.174.234]:64296)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:64296' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_3e293eea}
Connection to titan.picoctf.net closed.


```

## Notas adicionales

## Referencias


