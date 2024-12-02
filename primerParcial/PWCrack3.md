# Retos picoCTF

# Level PW Crack 3

## Objetivo
Can you crack the password to get the flag?
Download the password checker here and you'll need the encrypted flag and the hash in the same directory too.
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución
```
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ ls    
level3.flag.txt.enc  level3.hash.bin  level3.py
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ python level3.py 
Please enter correct password for flag: 7
That password is incorrect
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ vim level3.py 
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ bvi level3.hash.bin
Command 'bvi' not found, but can be installed with:
sudo apt install bvi
Do you want to install it? (N/y)y
sudo apt install bvi
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libnsl-dev libtirpc-dev
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  bvi
0 upgraded, 1 newly installed, 0 to remove and 2031 not upgraded.
Need to get 60.2 kB of archives.
After this operation, 156 kB of additional disk space will be used.
Get:1 http://kali.download/kali kali-rolling/main amd64 bvi amd64 1.4.2-2 [60.2 kB]
Fetched 60.2 kB in 1s (52.5 kB/s)
Selecting previously unselected package bvi.
(Reading database ... 413931 files and directories currently installed.)
Preparing to unpack .../archives/bvi_1.4.2-2_amd64.deb ...
Unpacking bvi (1.4.2-2) ...
Setting up bvi (1.4.2-2) ...
Processing triggers for kali-menu (2023.4.7) ...
Processing triggers for man-db (2.12.0-3) ...
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ bvi level3.hash.bin

bvi version 1.4.2 (C) GPL 1996-2023 by Gerhard Buergmann
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ vim level3.py      
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ cat level3.py  
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ python level3.py   
Please enter correct password for flag: f09e
That password is incorrect
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ python level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
                                                                         
┌──(kali㉿kali)-[~/Downloads/PWCrack3]
└─$ python level3.py                                        
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

```
## Notas adicionales

## Referencias


