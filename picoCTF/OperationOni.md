# Retos picoCTF

# Level Operation Oni

## Objetivo
Download this disk image, find the key and log into the remote machine.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download disk image
Remote machine: ssh -i key_file -p 58950 ctf-player@saturn.picoctf.net
## Solucion
'''
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ ls
disk.img.gz
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ gunzip disk.img.gz 
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ ls
disk.img
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ mmls disk.img    
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ fsstat -o 206848 disk.img  
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: Ext4
Volume Name: 
Volume ID: 9a1be2fb4beb97bede425f568c65d912

Last Written at: 2021-10-06 10:29:03 (EDT)
Last Checked at: 2021-10-06 10:28:55 (EDT)

Last Mounted at: 2021-10-06 10:29:48 (EDT)
Unmounted properly
Last mounted on: /

Source OS: Linux
Dynamic Structure
Compat Features: Journal, Ext Attributes, Resize Inode, Dir Index
InCompat Features: Filetype, Extents, 64bit, Flexible Block Groups, 
Read Only Compat Features: Sparse Super, Large File, Huge File, Extra Inode Size

Journal ID: 00
Journal Inode: 8

METADATA INFORMATION
--------------------------------------------
Inode Range: 1 - 33049
Root Directory: 2
Free Inodes: 30670
Inode Size: 256

CONTENT INFORMATION
--------------------------------------------
Block Groups Per Flex Group: 16
Block Range: 0 - 132095
Block Size: 1024
Reserved Blocks Before Block Groups: 1
Free Blocks: 22811

BLOCK GROUP INFORMATION
--------------------------------------------
Number of Block Groups: 17
Inodes per group: 1944
Blocks per group: 8192

Group: 0:
  Block Group Flags: [INODE_ZEROED] 
  Inode Range: 1 - 1944
  Block Range: 1 - 8192
  Layout:
    Super Block: 1 - 1
    Group Descriptor Table: 2 - 3
    Group Descriptor Growth Blocks: 4 - 259
    Data bitmap: 260 - 260
    Inode bitmap: 276 - 276
    Inode Table: 292 - 777
    Data Blocks: 8068 - 8192
  Free Inodes: 0 (0%)
  Free Blocks: 0 (0%)
  Total Directories: 224
  Stored Checksum: 0x4F82

Group: 1:
  Block Group Flags: [INODE_ZEROED] 
  Inode Range: 1945 - 3888
  Block Range: 8193 - 16384
  Layout:
    Super Block: 8193 - 8193
    Group Descriptor Table: 8194 - 8195
    Group Descriptor Growth Blocks: 8196 - 8451
    Data bitmap: 261 - 261
    Inode bitmap: 277 - 277
    Inode Table: 778 - 1263
    Data Blocks: 8452 - 16384
  Free Inodes: 1539 (79%)
  Free Blocks: 0 (0%)
  Total Directories: 121
  Stored Checksum: 0xD224

Group: 2:
  Block Group Flags: [INODE_ZEROED] 
  Inode Range: 3889 - 5832
  Block Range: 16385 - 24576
  Layout:
    Data bitmap: 262 - 262
    Inode bitmap: 278 - 278
    Inode Table: 1264 - 1749
    Data Blocks: 16385 - 24576
  Free Inodes: 1915 (98%)
  Free Blocks: 0 (0%)
  Total Directories: 29
  Stored Checksum: 0x7F59

Group: 3:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 5833 - 7776
  Block Range: 24577 - 32768
  Layout:
    Super Block: 24577 - 24577
    Group Descriptor Table: 24578 - 24579
    Group Descriptor Growth Blocks: 24580 - 24835
    Data bitmap: 263 - 263
    Inode bitmap: 279 - 279
    Inode Table: 1750 - 2235
    Data Blocks: 24836 - 32768
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0xAABD

Group: 4:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 7777 - 9720
  Block Range: 32769 - 40960
  Layout:
    Data bitmap: 264 - 264
    Inode bitmap: 280 - 280
    Inode Table: 2236 - 2721
    Data Blocks: 32769 - 40960
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0x6346

Group: 5:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 9721 - 11664
  Block Range: 40961 - 49152
  Layout:
    Super Block: 40961 - 40961
    Group Descriptor Table: 40962 - 40963
    Group Descriptor Growth Blocks: 40964 - 41219
    Data bitmap: 265 - 265
    Inode bitmap: 281 - 281
    Inode Table: 2722 - 3207
    Data Blocks: 41220 - 49152
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0x0093

Group: 6:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 11665 - 13608
  Block Range: 49153 - 57344
  Layout:
    Data bitmap: 266 - 266
    Inode bitmap: 282 - 282
    Inode Table: 3208 - 3693
    Data Blocks: 49153 - 57344
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0xE619

Group: 7:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 13609 - 15552
  Block Range: 57345 - 65536
  Layout:
    Super Block: 57345 - 57345
    Group Descriptor Table: 57346 - 57347
    Group Descriptor Growth Blocks: 57348 - 57603
    Data bitmap: 267 - 267
    Inode bitmap: 283 - 283
    Inode Table: 3694 - 4179
    Data Blocks: 57604 - 65536
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0xC52B

Group: 8:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 15553 - 17496
  Block Range: 65537 - 73728
  Layout:
    Data bitmap: 268 - 268
    Inode bitmap: 284 - 284
    Inode Table: 4180 - 4665
    Data Blocks: 65537 - 73728
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0xAEB3

Group: 9:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 17497 - 19440
  Block Range: 73729 - 81920
  Layout:
    Super Block: 73729 - 73729
    Group Descriptor Table: 73730 - 73731
    Group Descriptor Growth Blocks: 73732 - 73987
    Data bitmap: 269 - 269
    Inode bitmap: 285 - 285
    Inode Table: 4666 - 5151
    Data Blocks: 73988 - 81920
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0x786B

Group: 10:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 19441 - 21384
  Block Range: 81921 - 90112
  Layout:
    Data bitmap: 270 - 270
    Inode bitmap: 286 - 286
    Inode Table: 5152 - 5637
    Data Blocks: 81921 - 90112
  Free Inodes: 1944 (100%)
  Free Blocks: 279 (3%)
  Total Directories: 0
  Stored Checksum: 0x3AE8

Group: 11:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 21385 - 23328
  Block Range: 90113 - 98304
  Layout:
    Data bitmap: 271 - 271
    Inode bitmap: 287 - 287
    Inode Table: 5638 - 6123
    Data Blocks: 90113 - 98304
  Free Inodes: 1944 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0xC930

Group: 12:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 23329 - 25272
  Block Range: 98305 - 106496
  Layout:
    Data bitmap: 272 - 272
    Inode bitmap: 288 - 288
    Inode Table: 6124 - 6609
    Data Blocks: 98305 - 106496
  Free Inodes: 1944 (100%)
  Free Blocks: 428 (5%)
  Total Directories: 0
  Stored Checksum: 0x2818

Group: 13:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 25273 - 27216
  Block Range: 106497 - 114688
  Layout:
    Data bitmap: 273 - 273
    Inode bitmap: 289 - 289
    Inode Table: 6610 - 7095
    Data Blocks: 106497 - 114688
  Free Inodes: 1944 (100%)
  Free Blocks: 5185 (63%)
  Total Directories: 0
  Stored Checksum: 0x75C7

Group: 14:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 27217 - 29160
  Block Range: 114689 - 122880
  Layout:
    Data bitmap: 274 - 274
    Inode bitmap: 290 - 290
    Inode Table: 7096 - 7581
    Data Blocks: 114689 - 122880
  Free Inodes: 1944 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x1C2E

Group: 15:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 29161 - 31104
  Block Range: 122881 - 131072
  Layout:
    Data bitmap: 275 - 275
    Inode bitmap: 291 - 291
    Inode Table: 7582 - 8067
    Data Blocks: 122881 - 131072
  Free Inodes: 1944 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x8A66

Group: 16:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 31105 - 33048
  Block Range: 131073 - 132095
  Layout:
    Data bitmap: 131073 - 131073
    Inode bitmap: 131089 - 131089
    Inode Table: 131105 - 131590
    Uninit Data Bitmaps: 131074 - 131088
    Uninit Inode Bitmaps: 131090 - 131104
    Uninit Inode Table: 131591 - 138880
    Data Blocks: 138881 - 132095
  Free Inodes: 1944 (100%)
  Free Blocks: 535 (52%)
  Total Directories: 0
  Stored Checksum: 0xC5D2
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ fls -o 206848 disk.img     
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ fls -o 206848 disk.img 470 
r/r 2344:       .ash_history
d/d 3916:       .ssh
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ icat -o 206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ icat -o 206848 disk.img 2346
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGCtd7hso2E7OQItY6aTjMMyKZb1FVmeBfnVjyHcGYos root@localhost
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ icat -o 206848 disk.img 2345 > id_ed25519
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ ls
disk.img  id_ed25519
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ chmod 600 id_ed25519
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ ls -la
total 235564
drwxr-xr-x  2 kali kali      4096 Dec  2 20:05 .
drwxr-xr-x 81 kali kali     32768 Dec  2 19:40 ..
-rw-r--r--  1 kali kali 241172480 Aug  4  2023 disk.img
-rw-------  1 kali kali       411 Dec  2 20:05 id_ed25519
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ ssh -i id_ed25519 -p 60702 ctf-player@saturn.picoctf.net 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat 
.cache/   .ssh/     flag.txt  
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_af277f77}ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperationOni]
└─$ 

'''
## Referencias


