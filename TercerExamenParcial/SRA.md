# Retos picoCTF

# Level SRA

## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...
Connect to the program on our server: nc saturn.picoctf.net 65380
Download the program: chal.py

## Solucion
picoCTF{7h053_51n5_4r3_n0_m0r3_ba95c657}

```
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ wget https://artifacts.picoctf.net/c/294/chal.py
--2024-11-23 17:23:29--  https://artifacts.picoctf.net/c/294/chal.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 630 [application/octet-stream]
Saving to: ‘chal.py’

chal.py                             100%[===================================================================>]     630  --.-KB/s    in 0s      

2024-11-23 17:23:29 (13.1 MB/s) - ‘chal.py’ saved [630/630]

                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ cat chal.py    
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ nc saturn.picoctf.net 65380
anger = 43515754934120206648325202370996713463132331395497162073416257461754712629356
envy = 44616296960484452839959945849622681182975950859922310648355638319952945842113
vainglory?
> a
a
Hubris!
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ nc saturn.picoctf.net 65380
pride
    
pride

anger = 34720976107498316528285536763948804899210478752354142402225462607981832295701
envy = 5429377109878751039789841321944842167821095209104511403672243582861774534233
vainglory?
> Hubris!
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ nc saturn.picoctf.net 65380
anger = 9778306000587735677149345498693779247433995886687352398263523894304740128881
envy = 39956299356453436751394589040323897450701054883444079259169442690756302755137
vainglory?
> pride                          
pride
Hubris!
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ pip install pycryptodome   
Defaulting to user installation because normal site-packages is not writeable
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 24.3 will enforce this behaviour change. A possible replacement is to use pip for package installation.. Discussion can be found at https://github.com/pypa/pip/issues/12330         
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 24.3 will enforce this behaviour change. A possible replacement is to use pip for package installation.. Discussion can be found at https://github.com/pypa/pip/issues/12330                                                                                                                                          
Collecting pycryptodome                                                                                                                         
  Downloading pycryptodome-3.21.0-cp36-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (3.4 kB)
Downloading pycryptodome-3.21.0-cp36-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (2.3 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.3/2.3 MB 4.6 MB/s eta 0:00:00
Installing collected packages: pycryptodome
Successfully installed pycryptodome-3.21.0
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ vim superResolvedor.py
                                                                                                                                                
┌──(kali㉿kali)-[~/downloads/sra]
└─$ python superresolvedor.py 
[*] checking for new versions of pwntools
    to disable this functionality, set the contents of /home/kali/.cache/.pwntools-cache-3.11/update to 'never' (old way).
    or add the following lines to ~/.pwn.conf or ~/.config/pwn.conf (or /etc/pwn.conf system-wide):
        [update]
        interval=never
[*] you have the latest version of pwntools (4.13.1)
[-] opening connection to saturn.picoctf.net on port 60114: failed
[error] could not connect to saturn.picoctf.net on port 60114
traceback (most recent call last):
  file "/home/kali/downloads/sra/superresolvedor.py", line 14, in <module>
    con = remote("saturn.picoctf.net", 60114)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  file "/home/kali/.local/lib/python3.11/site-packages/pwnlib/tubes/remote.py", line 78, in __init__
    self.sock   = self._connect(fam, typ)
                  ^^^^^^^^^^^^^^^^^^^^^^^
  file "/home/kali/.local/lib/python3.11/site-packages/pwnlib/tubes/remote.py", line 127, in _connect
    self.error("could not connect to %s on port %s", self.rhost, self.rport)
  file "/home/kali/.local/lib/python3.11/site-packages/pwnlib/log.py", line 439, in error
    raise pwnlibexception(message % args)
pwnlib.exception.pwnlibexception: could not connect to saturn.picoctf.net on port 60114
                                                                                                                                                
┌──(kali㉿kali)-[~/downloads/sra]
└─$ vim superresolvedor.py   
                                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ python superResolvedor.py
[+] Opening connection to saturn.picoctf.net on port 65380: Done
Factoring...

sa
sa
as

sa
as
sa
sa
sa
yakusa
yakusa
sasasa
mesa
mesa
mesa que mas aplauda
mesa
mesa
mesa que mas aplauda    
le mando
le mando
pq se trabo  
pipipipipi     

┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ python superResolvedor.py                  
[+] Opening connection to saturn.picoctf.net on port 65380: Done
Factoring...
[*] Switching to interactive mode
eqDRX2WCtVKlGhWc
Conquered!
picoCTF{7h053_51n5_4r3_n0_m0r3_ba95c657}
[*] Got EOF while reading in interactive
$ que rollo biejones ajua, pura gente de chagoUAZ
$ 

┌──(kali㉿kali)-[~/Downloads/SRA]
└─$ cat superResolvedor.py                     
from sympy import factorint  # Importar factorint de sympy
from Crypto.Util.number import getPrime, inverse, bytes_to_long, isPrime, long_to_bytes  # Importar long_to_bytes
from string import ascii_letters, digits
from random import choice
from pwn import remote
from itertools import combinations
from functools import reduce

# Función para obtener el producto de una lista de números
def product(iterable):
    return reduce(lambda x, y: x * y, iterable, 1)

# Conectar al servidor
con = remote("saturn.picoctf.net", 65380)
e = 65537

# Obtener el ciphertext
con.recvuntil(b'anger = ')
c = int(con.readline().decode())

# Obtener d
con.recvuntil(b'envy = ')
d = int(con.readline().decode())

print('Factoring...')

# Intentar factorizar d*e - 1
fac = [a for a, b in list(factorint(d * e - 1).items()) for _ in range(b)]

# Intentar todas las combinaciones de factores
for r in range(2, len(fac)):
    for i in combinations(fac, r):
        p = product(i) + 1  # Producto de los factores más 1
        if p.bit_length() != 128 or not isPrime(p):
            continue
        m = long_to_bytes(pow(c, d, p))  # Decodificar el mensaje
        if len(m) != 16:
            continue
        con.recvuntil(b'> ')
        con.sendline(m)  # Enviar el mensaje decodificado
        con.interactive()  # Interactuar con el servidor

```


## Referencias


