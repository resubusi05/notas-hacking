# Retos picoCTF

# Level Commitment Issues 

## Objetivo
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:

## Solución

```
┌──(kali㉿kali)-[~/retosPico]
└─$ mkdir commitmentIssues        
                                                                        
┌──(kali㉿kali)-[~/retosPico]
└─$ cd commitmentIssues        
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues]
└─$ unzip challenge\(2\).zip
Archive:  challenge(2).zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/0e/
 extracting: drop-in/.git/objects/0e/0fefcdc9c9722914a7a9ecab1e88784f005eeb  
   creating: drop-in/.git/objects/5b/
 extracting: drop-in/.git/objects/5b/222fb49097fe9874695e8cc7cd9a6c80886017  
   creating: drop-in/.git/objects/b5/
 extracting: drop-in/.git/objects/b5/62f0b425907789d11d2fe2793e67592dc6be93  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/42/
 extracting: drop-in/.git/objects/42/942c9c605b30100f5d859ef6e172027447c0db  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues]
└─$ ls
'challenge(2).zip'   drop-in
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues]
└─$ cd drop-in         
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues/drop-in]
└─$ ls
message.txt
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues/drop-in]
└─$ cat message.txt 
TOP SECRET
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues/drop-in]
└─$ git log message.txt        
commit 42942c9c605b30100f5d859ef6e172027447c0db (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    remove sensitive info

commit b562f0b425907789d11d2fe2793e67592dc6be93
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    create flag
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues/drop-in]
└─$ git show HEAD      
commit 42942c9c605b30100f5d859ef6e172027447c0db (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index 0e0fefc..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_c785c319}
+TOP SECRET
                                                                        
┌──(kali㉿kali)-[~/retosPico/commitmentIssues/drop-in]
└─$ 

```

## Notas adicionales

## Referencias


