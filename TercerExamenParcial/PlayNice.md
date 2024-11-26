# Retos picoCTF

# Level Play Nice

## Objetivo
Not all ancient ciphers were so bad... The flag is not in standard format. nc mercury.picoctf.net 6057 playfair.py

## Solucion
2e71b99fd3d07af3808f8dff2652ae0e

Al conectar con el programa nos da una llave y el mensaje de encriptado.

Hay una herramienta en linea para este tipo de cifrado https://www.dcode.fr/playfair-cipher

```
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ wget https://mercury.picoctf.net/static/a48f79c95043804d1f43d5bfbffd324a/playfair.py
--2024-11-23 17:01:05--  https://mercury.picoctf.net/static/a48f79c95043804d1f43d5bfbffd324a/playfair.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1609 (1.6K) [application/octet-stream]
Saving to: ‘playfair.py’

playfair.py                         100%[===================================================================>]   1.57K  --.-KB/s    in 0s      

2024-11-23 17:01:06 (17.4 MB/s) - ‘playfair.py’ saved [1609/1609]

                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ cat playfair.py 
#!/usr/bin/python3 -u
import signal

SQUARE_SIZE = 6


def generate_square(alphabet):
        assert len(alphabet) == pow(SQUARE_SIZE, 2)
        matrix = []
        for i, letter in enumerate(alphabet):
                if i % SQUARE_SIZE == 0:
                        row = []
                row.append(letter)
                if i % SQUARE_SIZE == (SQUARE_SIZE - 1):
                        matrix.append(row)
        return matrix

def get_index(letter, matrix):
        for row in range(SQUARE_SIZE):
                for col in range(SQUARE_SIZE):
                        if matrix[row][col] == letter:
                                return (row, col)
        print("letter not found in matrix.")
        exit()

def encrypt_pair(pair, matrix):
        p1 = get_index(pair[0], matrix)
        p2 = get_index(pair[1], matrix)

        if p1[0] == p2[0]:
                return matrix[p1[0]][(p1[1] + 1)  % SQUARE_SIZE] + matrix[p2[0]][(p2[1] + 1)  % SQUARE_SIZE]
        elif p1[1] == p2[1]:
                return matrix[(p1[0] + 1)  % SQUARE_SIZE][p1[1]] + matrix[(p2[0] + 1)  % SQUARE_SIZE][p2[1]]
        else:
                return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]

def encrypt_string(s, matrix):
        result = ""
        if len(s) % 2 == 0:
                plain = s
        else:
                plain = s + "meiktp6yh4wxruavj9no13fb8d027c5glzsq"[0]
        for i in range(0, len(plain), 2):
                result += encrypt_pair(plain[i:i + 2], matrix)
        return result

alphabet = open("key").read().rstrip()
m = generate_square(alphabet)
msg = open("msg").read().rstrip()
enc_msg = encrypt_string(msg, m)
print("Here is the alphabet: {}\nHere is the encrypted message: {}".format(alphabet, enc_msg))
signal.alarm(18)
resp = input("What is the plaintext message? ").rstrip()
if resp and resp == msg:
        print("Congratulations! Here's the flag: {}".format(open("flag").read()))

# https://en.wikipedia.org/wiki/Playfair_cipher
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ nc mercury.picoctf.net 6057
Here is the alphabet: meiktp6yh4wxruavj9no13fb8d027c5glzsq
Here is the encrypted message: y7bcvefqecwfste224508y1ufb21ld
What is the plaintext message?                                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ nc mercury.picoctf.net 6057
Here is the alphabet: meiktp6yh4wxruavj9no13fb8d027c5glzsq
Here is the encrypted message: y7bcvefqecwfste224508y1ufb21ld
What is the plaintext message?                                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ nc mercury.picoctf.net 6057
Here is the alphabet: meiktp6yh4wxruavj9no13fb8d027c5glzsq
Here is the encrypted message: y7bcvefqecwfste224508y1ufb21ld
What is the plaintext message? HFJM3IR1KMTOPFRBF8
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> "print('WD9BUKBSPDTJ7SKD3KL8D6OA3F03G0'.lower())"
"print('WD9BUKBSPDTJ7SKD3KL8D6OA3F03G0'.lower())"
>>> print('WD9BUKBSPDTJ7SKD3KL8D6OA3F03G0'.lower())
wd9bukbspdtj7skd3kl8d6oa3f03g0
>>> exit()
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ nc mercury.picoctf.net 6057
Here is the alphabet: meiktp6yh4wxruavj9no13fb8d027c5glzsq
Here is the encrypted message: y7bcvefqecwfste224508y1ufb21ld
What is the plaintext message? wd9bukbspdtj7skd3kl8d6oa3f03g0
Congratulations! Here's the flag: 2e71b99fd3d07af3808f8dff2652ae0e
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/PlayNice]
└─$ 

```

## Referencias


