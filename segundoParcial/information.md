# Retos picoCTF

# Level information

## Objetivo
Files can always be changed in a secret way. Can you find the flag? cat.jpg
## Solucion
'''
┌──(kali㉿kali)-[~/Downloads/information]
└─$ ls
cat.jpg
                                                             
┌──(kali㉿kali)-[~/Downloads/information]
└─$ open cat.jpg 
                                                             
┌──(kali㉿kali)-[~/Downloads/information]
└─$ cp cat.jpg cat.txt           
                                                             
┌──(kali㉿kali)-[~/Downloads/information]
└─$ cat cat.txt             
����JFIF��0Photoshop 3.08BIMtPicoCTF��
                                      �http://ns.adobe.com/xap/1.0/<?xpacket begin='' id='W5M0MpCehiHzreSzNTczkc9d'?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 10.80'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>

 <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:license rdf:resource='cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
 </rdf:Description>

 <rdf:Description rdf:about=''
  xmlns:dc='http://purl.org/dc/elements/1.1/'>
  <dc:rights>
   <rdf:Alt>
    <rdf:li xml:lang='x-default'>PicoCTF</rdf:li>
   </rdf:Alt>
  </dc:rights>
 </rdf:Description>
</rdf:RDF>

'''

La modificar el archivo vemos que la bandera está como metadata encriptada

## Referencias


