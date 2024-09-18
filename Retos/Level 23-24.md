# Retos bandit

# Level 23

## Objetivo

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel
Contraseña del nivel: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

## Solución

Contraseña **bandit24**:  gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

```
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  e2scrub_all  otw-tmp-dir  sysstat
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat  /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ cd /home/bandit23
bandit23@bandit:~$ mkdir /tmp/kd
mkdir: cannot create directory ‘/tmp/kd’: File exists
bandit23@bandit:~$ chmod 777 /tmp/kd
bandit23@bandit:~$ cd /tmp/kd
bandit23@bandit:/tmp/kd$ ls
password  script.sh
bandit23@bandit:/tmp/kd$ cat password
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
bandit23@bandit:/tmp/kd$
```

## Notas




## Referencias


