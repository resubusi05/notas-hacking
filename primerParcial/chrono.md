# Retos picoCTF

# Level chrono

## Objetivo
How to automate tasks to run at intervals on linux servers?
Additional details will be available after launching your challenge instance.

## Solución
```
┌──(kali㉿kali)-[~/Downloads]
└─$ ssh picoplayer@saturn.picoctf.net -p 53248 
The authenticity of host '[saturn.picoctf.net]:53248 ([13.59.203.175]:53248)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:8: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:53248' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Permission denied, please try again.
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

picoplayer@challenge:~$ cd etc
-bash: cd: etc: No such file or directory
picoplayer@challenge:~$ ls
picoplayer@challenge:~$ cd ..
picoplayer@challenge:/home$ cd ..
picoplayer@challenge:/$ ls
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
picoplayer@challenge:/$ cd etc/
picoplayer@challenge:/etc$ la
.pwd.lock               init.d               rc1.d
adduser.conf            inputrc              rc2.d
alternatives            issue                rc3.d
apt                     issue.net            rc4.d
bash.bashrc             kernel               rc5.d
bindresvport.blacklist  ld.so.cache          rc6.d
binfmt.d                ld.so.conf           rcS.d
ca-certificates         ld.so.conf.d         resolv.conf
ca-certificates.conf    legal                rmt
cloud                   libaudit.conf        security
cron.d                  localtime            selinux
cron.daily              login.defs           shadow
cron.hourly             logrotate.d          shadow-
cron.monthly            lsb-release          shells
cron.weekly             machine-id           skel
crontab                 magic                ssh
dbus-1                  magic.mime           ssl
debconf.conf            mailcap              subgid
debian_version          mailcap.order        subgid-
default                 mime.types           subuid
deluser.conf            mke2fs.conf          subuid-
dhcp                    modules-load.d       sudoers
dpkg                    mtab                 sudoers.d
e2scrub.conf            networkd-dispatcher  sysctl.conf
environment             networks             sysctl.d
fstab                   nsswitch.conf        systemd
gai.conf                opt                  terminfo
group                   os-release           timezone
group-                  pam.conf             tmpfiles.d
gshadow                 pam.d                ucf.conf
gshadow-                passwd               ufw
gss                     passwd-              update-motd.d
host.conf               profile              wgetrc
hostname                profile.d            xattr.conf
hosts                   python3              xdg
hosts.allow             python3.8
hosts.deny              rc0.d
picoplayer@challenge:/etc$ ls
adduser.conf            init.d               rc0.d
alternatives            inputrc              rc1.d
apt                     issue                rc2.d
bash.bashrc             issue.net            rc3.d
bindresvport.blacklist  kernel               rc4.d
binfmt.d                ld.so.cache          rc5.d
ca-certificates         ld.so.conf           rc6.d
ca-certificates.conf    ld.so.conf.d         rcS.d
cloud                   legal                resolv.conf
cron.d                  libaudit.conf        rmt
cron.daily              localtime            security
cron.hourly             login.defs           selinux
cron.monthly            logrotate.d          shadow
cron.weekly             lsb-release          shadow-
crontab                 machine-id           shells
dbus-1                  magic                skel
debconf.conf            magic.mime           ssh
debian_version          mailcap              ssl
default                 mailcap.order        subgid
deluser.conf            mime.types           subgid-
dhcp                    mke2fs.conf          subuid
dpkg                    modules-load.d       subuid-
e2scrub.conf            mtab                 sudoers
environment             networkd-dispatcher  sudoers.d
fstab                   networks             sysctl.conf
gai.conf                nsswitch.conf        sysctl.d
group                   opt                  systemd
group-                  os-release           terminfo
gshadow                 pam.conf             timezone
gshadow-                pam.d                tmpfiles.d
gss                     passwd               ucf.conf
host.conf               passwd-              ufw
hostname                profile              update-motd.d
hosts                   profile.d            wgetrc
hosts.allow             python3              xattr.conf
hosts.deny              python3.8            xdg
picoplayer@challenge:/etc$ cat cron
cron.d/       cron.hourly/  cron.weekly/  
cron.daily/   cron.monthly/ crontab       
picoplayer@challenge:/etc$ cat crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}
picoplayer@challenge:/etc$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

## Notas adicionales

## Referencias


