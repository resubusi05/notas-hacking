# Retos picoCTF

# Level unpackme.py

## Objetivo
Can you get the flag?
Reverse engineer this Python program.

## Solucion
picoCTF{175_chr157m45_85f5d0ac}

```
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ cat unpackme.flag.py 
import base64
from cryptography.fernet import Fernet



payload = b'gAAAAABkzWGWvEp8gLI9AcIn5o-ahDUwkTvM6EwF7YYMZlE-_Gf9rcNYjxIgX4b0ltY6bcxKarib2ds6POclRwCwhsRb1LOXVt4Q3ePtMY4BmHFFZlIHLk05CjwigT7hiI9p3sH9e7Cpk1uO90xbHbuy-mfi3nkmn411aBgwxyWpJvykpkuBIG_nty6zbox3UhbB85TOis0TgM0zG4ht0-GUW4wTq2_5-wkw3kV1ZAisLJHzF-Z9oLMmwFZU0UCAcHaBTGDF5BnVLmUeCGTgzVLSNn6BmB61Yg=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
exec(plain.decode())
                                                                                            
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ vim unpackme.flag.py 
                                                                                            
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ python unpackme.flag.py
What's the password? d+
That password is incorrect.
None
                                                                                            
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ vim unpackme.flag.py   
                                                                                            
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ vim unpackme.flag.py   
                                                                                            
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ python unpackme.flag.py

pw = input('What\'s the password? ')

if pw == 'batteryhorse':
  print('picoCTF{175_chr157m45_85f5d0ac}')
else:
  print('That password is incorrect.')
```

```
┌──(kali㉿kali)-[~/Downloads/unpackmepy]
└─$ cat unpackme.flag.py   
import base64
from cryptography.fernet import Fernet



payload = b'gAAAAABkzWGWvEp8gLI9AcIn5o-ahDUwkTvM6EwF7YYMZlE-_Gf9rcNYjxIgX4b0ltY6bcxKarib2ds6POclRwCwhsRb1LOXVt4Q3ePtMY4BmHFFZlIHLk05CjwigT7hiI9p3sH9e7Cpk1uO90xbHbuy-mfi3nkmn411aBgwxyWpJvykpkuBIG_nty6zbox3UhbB85TOis0TgM0zG4ht0-GUW4wTq2_5-wkw3kV1ZAisLJHzF-Z9oLMmwFZU0UCAcHaBTGDF5BnVLmUeCGTgzVLSNn6BmB61Yg=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
print(plain.decode())
```
## Referencias


