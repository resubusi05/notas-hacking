# Retos picoCTF

# Level Blame Game

## Objetivo
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

    challenge.zip


## Solución
```
┌──(kali㉿kali)-[~/Downloads]
└─$ ls                                       
'big-zip-files(1).zip'   challenge.zip
 big-zip-files.zip       drop-in
'challenge(1).zip'
                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cd drop-in         
                                                   
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git log -p -- message.py                 
commit 0351e0474493168ca76441c24630c17554fd09ca
Author: picoCTF{@sk_th3_1nt3rn_d2d29f22} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:01 2024 +0000

    optimize file size of prod code

diff --git a/message.py b/message.py
index 7df869a..326544a 100644
--- a/message.py
+++ b/message.py
@@ -1 +1 @@
-print("Hello, World!")
+print("Hello, World!"

commit c9e851509190f5887e91339ee18087e3e77ebfda
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:01 2024 +0000

    create top secret project

diff --git a/message.py b/message.py
new file mode 100644
index 0000000..7df869a
--- /dev/null
+++ b/message.py

commit 0351e0474493168ca76441c24630c17554fd09ca
Author: picoCTF{@sk_th3_1nt3rn_d2d29f22} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:01 2024 +0000

    optimize file size of prod code

diff --git a/message.py b/message.py
index 7df869a..326544a 100644
--- a/message.py
+++ b/message.py
@@ -1 +1 @@
-print("Hello, World!")
+print("Hello, World!"

commit c9e851509190f5887e91339ee18087e3e77ebfda
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:01 2024 +0000

    create top secret project

diff --git a/message.py b/message.py
new file mode 100644
index 0000000..7df869a
--- /dev/null
+++ b/message.py
@@ -0,0 +1 @@

```


## Notas adicionales

## Referencias


