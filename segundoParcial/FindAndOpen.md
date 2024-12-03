# Retos picoCTF

# Level FindAndOpen

## Objetivo
Someone might have hidden the password in the trace file.
Find the key to unlock this file. This tracefile might be good to analyze.
## Solucion
Al ver un poco el archivo .pcap, me encuentro un fragmento de la bandera, usé ese fragmento como contraseña deñ .zip y si, esa era la contraseña, dandonos la bandera.

´´´
                                                         
┌──(kali㉿kali)-[~/Downloads/FindAndOpen]
└─$ unzip flag.zip          
Archive:  flag.zip
[flag.zip] flag password: 
password incorrect--reenter: 
 extracting: flag                     bad CRC c198c0bfhould be f74454b1)
    (may instead be incorrect password)
                                                      
┌──(kali㉿kali)-[~/Downloads/FindAndOpen]
└─$ unzip flag.zip
Archive:  flag.zip
[flag.zip] flag password: 
replace flag? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
 extracting: flag                    
                                                      
┌──(kali㉿kali)-[~/Downloads/FindAndOpen]
└─$ ls 
dump.pcap  flag  flag.zip
                                                      
┌──(kali㉿kali)-[~/Downloads/FindAndOpen]
└─$ cat flag              
picoCTF{R34DING_LOKd_fil56_succ3ss_5ed3a878}
                                                      
┌──(kali㉿kali)-[~/
´´´

## Referencias


