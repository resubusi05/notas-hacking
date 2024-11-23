# Retos picoCTF

# Level Mr-Worldwide

## Objetivo
A musician left us a message. What's it mean?

## Solucion
picoCTF{KODIAK_ALASKA}
```
──(kali㉿kali)-[~/Downloads]
└─$ cd Mr-Worldwide 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ ls
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ wget https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt 
--2024-11-23 00:45:31--  https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 278 [application/octet-stream]
Saving to: ‘message.txt’

message.txt              100%[=================================>]     278  --.-KB/s    in 0s      

2024-11-23 00:45:32 (7.90 MB/s) - ‘message.txt’ saved [278/278]

                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ ls
message.txt
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ cat message.txt 
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ vim resolvedor.py
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ cat resolvedor.py 
import requests, re

flag = "picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}"

def get_letter_from_coordinate(match):
    lat = match.group(1)
    long = match.group(2)
    r = requests.get("https://geocode.xyz/{},{}?json=1".format(lat, long))
    j = r.json()
    return j["geocode"][0]

print re.sub(r'\(([\d\.-]+), ([\d\.-]+)\)', get_letter_from_coordinate, flag)
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ python resolvedor.py 
  File "/home/kali/Downloads/Mr-Worldwide/resolvedor.py", line 12
    print re.sub(r'\(([\d\.-]+), ([\d\.-]+)\)', get_letter_from_coordinate, flag)
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ vim resolvedor.py   
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ python resolvedor.py
  File "/home/kali/Downloads/Mr-Worldwide/resolvedor.py", line 12
    print( re.sub(r'\(([\d\.-]+), ([\d\.-]+)\)', get_letter_from_coordinate, flag)
         ^
SyntaxError: '(' was never closed
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ vim resolvedor.py   
                                                                                                   
┌──(kali㉿kali)-[~/Downloads/Mr-Worldwide]
└─$ python resolvedor.py
picoCTF{KODIAK_ALANKA}
```

## Referencias


