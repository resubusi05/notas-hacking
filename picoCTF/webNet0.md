# Retos picoCTF

# Level WebNet0

## Objetivo
We found this packet capture and key. Recover the flag.

## Solucion

```
┌──(kali㉿kali)-[~/Downloads/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
--2024-10-10 20:57:29--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[=================>]  12.85K  --.-KB/s    in 0s      

2024-10-10 20:57:30 (169 MB/s) - ‘capture.pcap’ saved [13163/13163]

                                                                              
┌──(kali㉿kali)-[~/Downloads/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key 
--2024-10-10 20:57:45--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key        100%[=================>]   1.66K  --.-KB/s    in 0s      

2024-10-10 20:57:46 (43.6 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                              
┌──(kali㉿kali)-[~/Downloads/WebNet0]
└─$ ls
capture.pcap  picopico.key
                                                                              
┌──(kali㉿kali)-[~/Downloads/WebNet0]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le

```


## Referencias


