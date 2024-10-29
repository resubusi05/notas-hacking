# Retos picoCTF

# Level Bookmarklet

## Objetivo
Why search for the flag when I can make a bookmarklet to print it for me?

Additional details will be available after launching your challenge instance.

## Solucion
picoCTF{p@g3_turn3r_e8b2d43b}

Se ve el codigo fuente de la pagina y encontramos na funcion javascript para desencriptar la bandera y al poner esta funcion en el navegador, nos da la bandera.

```
javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓË¨ËÓ§Èí";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
```

## Referencias


