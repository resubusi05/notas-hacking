# Retos picoCTF

# Level Matryoshka doll

## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: this

## Solucion
```
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll]
└─$ wget https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg              
--2024-10-10 23:00:26--  https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651622 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg           100%[=================>] 636.35K  1003KB/s    in 0.6s    

2024-10-10 23:00:28 (1003 KB/s) - ‘dolls.jpg’ saved [651622/651622]

                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll]
└─$ open dolls.jpg 
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll]
└─$ unzip dolls.jpg 
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll]
└─$ ls
base_images  dolls.jpg
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll]
└─$ cd base_images   
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images]
└─$ ls
2_c.jpg
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images]
└─$ open 2_c.jpg 
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images]
└─$ unzip 2_c.jpg  
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images]
└─$ ls            
2_c.jpg  base_images
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images]
└─$ cd base_images 
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images/base_images]
└─$ ls
3_c.jpg
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images/base_images]
└─$ open 3_c.jpg 
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images/base_images]
└─$ unzip 3_c.jpg 
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
                                                                              
┌──(kali㉿kali)-[~/Downloads/matryoshkaDoll/base_images/base_images]
└─$ cd base_images 
                                                                              
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ open 3_c.jpg
Completing external command
obexctl                oLschema2ldif          openvpn              
obj2yaml-16            omfonts                openvt               
objcopy                on_ac_power            ophcrack             
objdump                onboard                ophcrack-cli         
obsidian               onboard-settings       opl2ofm              
oclock                 onesixtyone            opt-16               
ocsptool               open                   orca                 
od                     openbsd_softraid2john  orca-dm-wrapper      
odf2mht                openconnect            osage                
odf2xhtml              openfortivpn           ospd-openvas         
odf2xml                openpgp-tool           os-prober            
odfimgimport           opensc-asn1            otangle              
odflint                opensc-explorer        otp2ocp              
odfmeta                opensc-notify          out123               
odfoutline             opensc-tool            outocp               
odfuserfield           openssl                ovf2ovp              
odvicopy               openssl2john           ovp2ovf              
odvitype               openvas                ownership            
office2john            openvas-nasl                                
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ open 4_c.jpg
                                                                              
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ ls
4_c.jpg
                                                                              
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ unzip 4_c.jpg 
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
                                                                              
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ ls           
4_c.jpg  flag.txt
                                                                              
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ cat flag.txt  
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}                                                                              
┌──(kali㉿kali)-[~/…/matryoshkaDoll/base_images/base_images/base_images]
└─$ 

```
## Referencias


