# Retos picoCTF

# Level Wave a flag

## Objetivo
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

## Solución
```                                                                                         
┌─(kali㉿kali)-[~/Downloads/Waveaflag]
└─$ ls -la                      
total 48
drwxr-xr-x  2 kali kali  4096 Dec  1 21:03 .
drwxr-xr-x 70 kali kali 32768 Dec  1 21:03 ..
-rwxrwxrwx  1 kali kali 10936 Mar 15  2021 warm
                                                                                             
┌──(kali㉿kali)-[~/Downloads/Waveaflag]
└─$ ./warm   
Hello user! Pass me a -h to learn what I can do!
                                                                                             
┌──(kali㉿kali)-[~/Downloads/Waveaflag]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
                                                                                             
┌──(kali㉿kali)-[~/Downloads/Waveaflag]
└─$ 
```

## Notas adicionales

## Referencias


