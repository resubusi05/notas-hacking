# Retos picoCTF

# Level basix-mod1

## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message here. Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

## Solucion

```
data = open('message.txt','r').read().split()
flag = ''
for c in data:
    char = int(c) % 37

    if char >= 0 and char<=25:
        s = chr(char+65)
    elif char >=26 and char <=35:
        s = chr(char+22)
    elif char == 36:
        s = '_'

    flag += s
    print(s)

print(flag)

```

## Referencias


