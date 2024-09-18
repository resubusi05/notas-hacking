# Retos bandit

# Level 20

## Objetivo

Hay un programa que regula automáticamente en intervalos regulares desde cron. Ve en ==/etc/cron.d/== para la configuración y ve que comando se esta ejecutando.
 
## Datos de acceso al nivel
Contraseña del nivel: EeoULMCra2q0dSkYj561DX7s1CpBuOBt

## Solución

Contraseña **bandit22**:  tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

Se accede al nivel.

Nos vamos a ==etc/cron.d== para ver los comandos que se esten ejecutando.

```
bandit21@bandit:/etc/cron.d$ ls -la
total 44
drwxr-xr-x   2 root root  4096 Jul 17 15:59 .
drwxr-xr-x 121 root root 12288 Aug  1 14:49 ..
-rw-r--r--   1 root root   120 Jul 17 15:57 cronjob_bandit22
-rw-r--r--   1 root root   122 Jul 17 15:57 cronjob_bandit23
-rw-r--r--   1 root root   120 Jul 17 15:57 cronjob_bandit24
-rw-r--r--   1 root root   201 Apr  8 14:38 e2scrub_all
-rwx------   1 root root    52 Jul 17 15:59 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 31 00:06 .placeholder
-rw-r--r--   1 root root   396 Jan  9  2024 sysstat
```

Abrimos **cronjob_bandit22** con cat.

```
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```

Nos vamos a ==usr/bin== para bucar el .sh y estando ahí usamos cat para abrirlo.

  ```
  bandit21@bandit:/usr/bin$ cat cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/usr/bin$
```

Abrimos  el archivo **tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q** para ver lo que contiene y está la contraseña.

```
bandit21@bandit:/tmp$ cat t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
bandit21@bandit:/tmp$
```

## Notas


## Referencias


