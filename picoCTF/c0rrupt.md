# Retos picoCTF

# Level c0rrupt

## Objetivo
We found this file. Recover the flag.

## Solucion
picoCTF{c0rrupt10n_187995}

```
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo apt install pngcheck
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libnsl-dev libtirpc-dev
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  pngcheck
0 upgraded, 1 newly installed, 0 to remove and 1804 not upgraded.
Need to get 68.6 kB of archives.
After this operation, 208 kB of additional disk space will be used.
Err:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3
  403  Forbidden [IP: 104.17.254.239 80]
E: Failed to fetch http://kali.download/kali/pool/main/p/pngcheck/pngcheck_3.0.3-3_amd64.deb  403  Forbidden [IP: 104.17.254.239 80]
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v flag.png     
Command 'pngcheck' not found, but can be installed with:
sudo apt install pngcheck
Do you want to install it? (N/y)n
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor flag.png
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v flag.png     
Command 'pngcheck' not found, but can be installed with:
sudo apt install pngcheck
Do you want to install it? (N/y)n
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor flag.png  
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor flag.png
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ open flag.png     
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor flag.png
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ open flag.png     
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor flag.png
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ open flag.png     
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor flag.png
                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ open flag.png     
                                                                
```


## Referencias


