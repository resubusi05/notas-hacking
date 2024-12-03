# Retos picoCTF

# Level Disk, disk, sleuth!
## Objetivo
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: dds1-alpine.flag.img.gz
## Solucion
'''
┌──(kali㉿kali)-[~/Downloads/Diskdisksleuth]
└─$ ls
dds1-alpine.flag.img
                                                                  
┌──(kali㉿kali)-[~/Downloads/Diskdisksleuth]
└─$ open dds1-alpine.flag.img 
                                                                  
┌──(kali㉿kali)-[~/Downloads/Diskdisksleuth]
└─$ file dds1-alpine.flag.img   
dds1-alpine.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0x10,81,1), startsector 2048, 260096 sectors
                                                                  
┌──(kali㉿kali)-[~/Downloads/Diskdisksleuth]
└─$ autopsy -v
Invalid flag: -v


usage: /usr/bin/autopsy [-c] [-C] [-d evid_locker] [-i device filesystem mnt] [-p port] [remoteaddr]
  -c: force a cookie in the URL
  -C: force NO cookie in the URL
  -d dir: specify the evidence locker directory
  -i device filesystem mnt: Specify info for live analysis
  -p port: specify the server port (default: 9999)
  remoteaddr: specify the host with the browser (default: localhost)
                                                                  
┌──(kali㉿kali)-[~/Downloads/Diskdisksleuth]
└─$ srch_strings dds1-alpine.flag.img | grep 'picoCTF'
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_a011c142}
                                                                  
┌──(kali㉿kali)-[~/Downloads/Diskdisksleuth]
└─$ 

'''

## Referencias


