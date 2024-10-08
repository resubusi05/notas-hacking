# Retos picoCTF

# Level shark on wire 2

## Objetivo
We found this packet capture. Recover the flag that was pilfered from the network.

## Solucion
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```
# pip install scapy
from scapy.all import *

flag = ""

packets = rdpcap('capture.pcap')

for packet in packets:
    # if the packet is a UDP packet going to point 22
    if UDP in packet and packet[UDP].dport == 22:
        flag += chr(packet[UDP].sport - 5000)
print("Flag: {}".format(flag))

```

## Referencias


