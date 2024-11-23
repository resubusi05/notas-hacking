# Retos picoCTF

# Level New Caesar

## Objetivo
We found a brand new type of encryption, can you break the secret code? (Wrap with picoCTF{}) lkmjkemjmkiekeijiiigljlhilihliikiliginliljimiklligljiflhiniiiniiihlhilimlhijil new_caesar.py

## Solucion
picoCTF{et_tu?_431db62c5618cd75f1d0b83832b67b46}

```
┌──(kali㉿kali)-[~/Downloads]
└─$ mkdir NewCaesar                                                                        
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cd NewCaesar/ 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ wget https://mercury.picoctf.net/static/c9043977604318594ab73d126a01d0b1/new_caesar.py
--2024-11-23 00:52:20--  https://mercury.picoctf.net/static/c9043977604318594ab73d126a01d0b1/new_caesar.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 589 [application/octet-stream]
Saving to: ‘new_caesar.py’

new_caesar.py            100%[=================================>]     589  --.-KB/s    in 0s      

2024-11-23 00:52:21 (15.0 MB/s) - ‘new_caesar.py’ saved [589/589]

                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ ls
new_caesar.py
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ python new_caesar.py 
Traceback (most recent call last):
  File "/home/kali/Downloads/NewCaesar/new_caesar.py", line 21, in <module>
    assert all([k in ALPHABET for k in key])
AssertionError
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ cat new_caesar.py 
import string

LOWERCASE_OFFSET = ord("a")
ALPHABET = string.ascii_lowercase[:16]

def b16_encode(plain):
        enc = ""
        for c in plain:
                binary = "{0:08b}".format(ord(c))
                enc += ALPHABET[int(binary[:4], 2)]
                enc += ALPHABET[int(binary[4:], 2)]
        return enc

def shift(c, k):
        t1 = ord(c) - LOWERCASE_OFFSET
        t2 = ord(k) - LOWERCASE_OFFSET
        return ALPHABET[(t1 + t2) % len(ALPHABET)]

flag = "redacted"
key = "redacted"
assert all([k in ALPHABET for k in key])
assert len(key) == 1

b16 = b16_encode(flag)
enc = ""
for i, c in enumerate(b16):
        enc += shift(c, key[i % len(key)])
print(enc)
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ vim caesar2.py   
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ python caesar2.py   
Key: e, Plaintext: et_tu?_1ac5f3d7920a85610afeb2572831daa8
Key: f, Plaintext: TcNcd.N PR$U"S&(!/P'$% /PUTQ!$&!'" SPP'
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ vim caesar2.py   
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/NewCaesar]
└─$ python caesar2.py
Key: f, Plaintext: et_tu?_431db62c5618cd75f1d0b83832b67b46
Key: g, Plaintext: TcNcd.N#" SQ%!R$% 'RS&$U S/Q'"'"!Q%&Q#%
 
```

## Referencias


