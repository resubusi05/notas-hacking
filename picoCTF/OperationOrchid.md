# Retos picoCTF

# Level Operation Orchid

## Objetivo
Download this disk image and find the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download compressed disk image

## Solucion

'''
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ ls    
disk.flag.img.gz
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ gunzip disk.flag.img.gz 
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ ls
disk.flag.img
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ mmls disk.flag.img  
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fsstat -o 2048 disk.flag.img 
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: Ext4
Volume Name: 
Volume ID: d5f34acbb90977bb7e47d5fe07246a49

Last Written at: 2021-10-06 14:33:27 (EDT)
Last Checked at: 2021-10-06 14:20:47 (EDT)

Last Mounted at: 2021-10-06 14:30:15 (EDT)
Unmounted properly
Last mounted on: /mnt/boot

Source OS: Linux
Dynamic Structure
Compat Features: Journal, Ext Attributes, Resize Inode, Dir Index
InCompat Features: Filetype, Extents, Flexible Block Groups, 
Read Only Compat Features: Sparse Super, Large File, Huge File, Extra Inode Size

Journal ID: 00
Journal Inode: 8

METADATA INFORMATION
--------------------------------------------
Inode Range: 1 - 25585
Root Directory: 2
Free Inodes: 25560
Inode Size: 256

CONTENT INFORMATION
--------------------------------------------
Block Groups Per Flex Group: 16
Block Range: 0 - 102399
Block Size: 1024
Reserved Blocks Before Block Groups: 1
Free Blocks: 74579

BLOCK GROUP INFORMATION
--------------------------------------------
Number of Block Groups: 13
Inodes per group: 1968
Blocks per group: 8192

Group: 0:
  Inode Range: 1 - 1968
  Block Range: 1 - 8192
  Layout:
    Super Block: 1 - 1
    Group Descriptor Table: 2 - 2
    Group Descriptor Growth Blocks: 3 - 258
    Data bitmap: 259 - 259
    Inode bitmap: 272 - 272
    Inode Table: 285 - 776
    Data Blocks: 777 - 8192
  Free Inodes: 1944 (98%)
  Free Blocks: 1498 (18%)
  Total Directories: 2

Group: 1:
  Inode Range: 1969 - 3936
  Block Range: 8193 - 16384
  Layout:
    Super Block: 8193 - 8193
    Group Descriptor Table: 8194 - 8194
    Group Descriptor Growth Blocks: 8195 - 8450
    Data bitmap: 260 - 260
    Inode bitmap: 273 - 273
    Inode Table: 777 - 1268
    Data Blocks: 1269 - 16384
  Free Inodes: 1968 (100%)
  Free Blocks: 7548 (92%)
  Total Directories: 0

Group: 2:
  Inode Range: 3937 - 5904
  Block Range: 16385 - 24576
  Layout:
    Data bitmap: 261 - 261
    Inode bitmap: 274 - 274
    Inode Table: 1269 - 1760
    Data Blocks: 1761 - 24576
  Free Inodes: 1968 (100%)
  Free Blocks: 4644 (56%)
  Total Directories: 0

Group: 3:
  Inode Range: 5905 - 7872
  Block Range: 24577 - 32768
  Layout:
    Super Block: 24577 - 24577
    Group Descriptor Table: 24578 - 24578
    Group Descriptor Growth Blocks: 24579 - 24834
    Data bitmap: 262 - 262
    Inode bitmap: 275 - 275
    Inode Table: 1761 - 2252
    Data Blocks: 2253 - 32768
  Free Inodes: 1968 (100%)
  Free Blocks: 1884 (22%)
  Total Directories: 0

Group: 4:
  Inode Range: 7873 - 9840
  Block Range: 32769 - 40960
  Layout:
    Data bitmap: 263 - 263
    Inode bitmap: 276 - 276
    Inode Table: 2253 - 2744
    Data Blocks: 2745 - 40960
  Free Inodes: 1968 (100%)
  Free Blocks: 2436 (29%)
  Total Directories: 0

Group: 5:
  Inode Range: 9841 - 11808
  Block Range: 40961 - 49152
  Layout:
    Super Block: 40961 - 40961
    Group Descriptor Table: 40962 - 40962
    Group Descriptor Growth Blocks: 40963 - 41218
    Data bitmap: 264 - 264
    Inode bitmap: 277 - 277
    Inode Table: 2745 - 3236
    Data Blocks: 3237 - 49152
  Free Inodes: 1968 (100%)
  Free Blocks: 7934 (96%)
  Total Directories: 0

Group: 6:
  Inode Range: 11809 - 13776
  Block Range: 49153 - 57344
  Layout:
    Data bitmap: 265 - 265
    Inode bitmap: 278 - 278
    Inode Table: 3237 - 3728
    Data Blocks: 3729 - 57344
  Free Inodes: 1968 (100%)
  Free Blocks: 4096 (50%)
  Total Directories: 0

Group: 7:
  Inode Range: 13777 - 15744
  Block Range: 57345 - 65536
  Layout:
    Super Block: 57345 - 57345
    Group Descriptor Table: 57346 - 57346
    Group Descriptor Growth Blocks: 57347 - 57602
    Data bitmap: 266 - 266
    Inode bitmap: 279 - 279
    Inode Table: 3729 - 4220
    Data Blocks: 4221 - 65536
  Free Inodes: 1968 (100%)
  Free Blocks: 7934 (96%)
  Total Directories: 0

Group: 8:
  Inode Range: 15745 - 17712
  Block Range: 65537 - 73728
  Layout:
    Data bitmap: 267 - 267
    Inode bitmap: 280 - 280
    Inode Table: 4221 - 4712
    Data Blocks: 4713 - 73728
  Free Inodes: 1968 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0

Group: 9:
  Inode Range: 17713 - 19680
  Block Range: 73729 - 81920
  Layout:
    Super Block: 73729 - 73729
    Group Descriptor Table: 73730 - 73730
    Group Descriptor Growth Blocks: 73731 - 73986
    Data bitmap: 268 - 268
    Inode bitmap: 281 - 281
    Inode Table: 4713 - 5204
    Data Blocks: 5205 - 81920
  Free Inodes: 1968 (100%)
  Free Blocks: 7934 (96%)
  Total Directories: 0

Group: 10:
  Inode Range: 19681 - 21648
  Block Range: 81921 - 90112
  Layout:
    Data bitmap: 269 - 269
    Inode bitmap: 282 - 282
    Inode Table: 5205 - 5696
    Data Blocks: 5697 - 90112
  Free Inodes: 1968 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0

Group: 11:
  Inode Range: 21649 - 23616
  Block Range: 90113 - 98304
  Layout:
    Data bitmap: 270 - 270
    Inode bitmap: 283 - 283
    Inode Table: 5697 - 6188
    Data Blocks: 6189 - 98304
  Free Inodes: 1968 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0

Group: 12:
  Inode Range: 23617 - 25584
  Block Range: 98305 - 102399
  Layout:
    Data bitmap: 271 - 271
    Inode bitmap: 284 - 284
    Inode Table: 6189 - 6680
    Data Blocks: 6681 - 102399
  Free Inodes: 1968 (100%)
  Free Blocks: 4095 (99%)
  Total Directories: 0
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fls -o 2048 disk.img     
Error stat(ing) image file (raw_open: image "disk.img" - No such file or directory)
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fls -o 2048 disk.flag.img 
d/d 11: lost+found
r/r 12: ldlinux.sys
r/r 13: ldlinux.c32
r/r 15: config-virt
r/r 16: vmlinuz-virt
r/r 17: initramfs-virt
l/l 18: boot
r/r 20: libutil.c32
r/r 19: extlinux.conf
r/r 21: libcom32.c32
r/r 22: mboot.c32
r/r 23: menu.c32
r/r 14: System.map-virt
r/r 24: vesamenu.c32
V/V 25585:      $OrphanFiles
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fls -o 206848 disk.flag.img
Cannot determine file system type
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fsstat -o 206848 disk.flag.img
Cannot determine file system type
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fsstat -o 411648  disk.flag.img 
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: Ext4
Volume Name: 
Volume ID: 9e25d4c2eb360d83644eb5b17186687b

Last Written at: 2021-10-06 14:20:56 (EDT)
Last Checked at: 2021-10-06 14:20:47 (EDT)

Last Mounted at: 2021-10-06 14:30:15 (EDT)
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
Inode Range: 1 - 51001
Root Directory: 2
Free Inodes: 48614
Inode Size: 256

CONTENT INFORMATION
--------------------------------------------
Block Groups Per Flex Group: 16
Block Range: 0 - 203775
Block Size: 1024
Reserved Blocks Before Block Groups: 1
Free Blocks: 82711

BLOCK GROUP INFORMATION
--------------------------------------------
Number of Block Groups: 25
Inodes per group: 2040
Blocks per group: 8192

Group: 0:
  Block Group Flags: [INODE_ZEROED] 
  Inode Range: 1 - 2040
  Block Range: 1 - 8192
  Layout:
    Super Block: 1 - 1
    Group Descriptor Table: 2 - 3
    Group Descriptor Growth Blocks: 4 - 259
    Data bitmap: 260 - 260
    Inode bitmap: 276 - 276
    Inode Table: 292 - 801
    Data Blocks: 8452 - 8192
  Free Inodes: 153 (7%)
  Free Blocks: 0 (0%)
  Total Directories: 292
  Stored Checksum: 0x3D70

Group: 1:
  Block Group Flags: [INODE_ZEROED] 
  Inode Range: 2041 - 4080
  Block Range: 8193 - 16384
  Layout:
    Super Block: 8193 - 8193
    Group Descriptor Table: 8194 - 8195
    Group Descriptor Growth Blocks: 8196 - 8451
    Data bitmap: 261 - 261
    Inode bitmap: 277 - 277
    Inode Table: 802 - 1311
    Data Blocks: 8452 - 16384
  Free Inodes: 2039 (99%)
  Free Blocks: 18 (0%)
  Total Directories: 1
  Stored Checksum: 0xC49B

Group: 2:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 4081 - 6120
  Block Range: 16385 - 24576
  Layout:
    Data bitmap: 262 - 262
    Inode bitmap: 278 - 278
    Inode Table: 1312 - 1821
    Data Blocks: 16385 - 24576
  Free Inodes: 2040 (100%)
  Free Blocks: 23 (0%)
  Total Directories: 0
  Stored Checksum: 0xA9E1

Group: 3:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 6121 - 8160
  Block Range: 24577 - 32768
  Layout:
    Super Block: 24577 - 24577
    Group Descriptor Table: 24578 - 24579
    Group Descriptor Growth Blocks: 24580 - 24835
    Data bitmap: 263 - 263
    Inode bitmap: 279 - 279
    Inode Table: 1822 - 2331
    Data Blocks: 24836 - 32768
  Free Inodes: 2040 (100%)
  Free Blocks: 0 (0%)
  Total Directories: 0
  Stored Checksum: 0x6C20

Group: 4:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 8161 - 10200
  Block Range: 32769 - 40960
  Layout:
    Data bitmap: 264 - 264
    Inode bitmap: 280 - 280
    Inode Table: 2332 - 2841
    Data Blocks: 32769 - 40960
  Free Inodes: 2040 (100%)
  Free Blocks: 6 (0%)
  Total Directories: 0
  Stored Checksum: 0xA1B4

Group: 5:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 10201 - 12240
  Block Range: 40961 - 49152
  Layout:
    Super Block: 40961 - 40961
    Group Descriptor Table: 40962 - 40963
    Group Descriptor Growth Blocks: 40964 - 41219
    Data bitmap: 265 - 265
    Inode bitmap: 281 - 281
    Inode Table: 2842 - 3351
    Data Blocks: 41220 - 49152
  Free Inodes: 2040 (100%)
  Free Blocks: 1 (0%)
  Total Directories: 0
  Stored Checksum: 0x998D

Group: 6:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 12241 - 14280
  Block Range: 49153 - 57344
  Layout:
    Data bitmap: 266 - 266
    Inode bitmap: 282 - 282
    Inode Table: 3352 - 3861
    Data Blocks: 49153 - 57344
  Free Inodes: 2040 (100%)
  Free Blocks: 3 (0%)
  Total Directories: 0
  Stored Checksum: 0xEA29

Group: 7:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 14281 - 16320
  Block Range: 57345 - 65536
  Layout:
    Super Block: 57345 - 57345
    Group Descriptor Table: 57346 - 57347
    Group Descriptor Growth Blocks: 57348 - 57603
    Data bitmap: 267 - 267
    Inode bitmap: 283 - 283
    Inode Table: 3862 - 4371
    Data Blocks: 57604 - 65536
  Free Inodes: 2040 (100%)
  Free Blocks: 18 (0%)
  Total Directories: 0
  Stored Checksum: 0xFC8F

Group: 8:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 16321 - 18360
  Block Range: 65537 - 73728
  Layout:
    Data bitmap: 268 - 268
    Inode bitmap: 284 - 284
    Inode Table: 4372 - 4881
    Data Blocks: 65537 - 73728
  Free Inodes: 2040 (100%)
  Free Blocks: 72 (0%)
  Total Directories: 0
  Stored Checksum: 0xB347

Group: 9:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 18361 - 20400
  Block Range: 73729 - 81920
  Layout:
    Super Block: 73729 - 73729
    Group Descriptor Table: 73730 - 73731
    Group Descriptor Growth Blocks: 73732 - 73987
    Data bitmap: 269 - 269
    Inode bitmap: 285 - 285
    Inode Table: 4882 - 5391
    Data Blocks: 73988 - 81920
  Free Inodes: 2040 (100%)
  Free Blocks: 1 (0%)
  Total Directories: 0
  Stored Checksum: 0xC440

Group: 10:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 20401 - 22440
  Block Range: 81921 - 90112
  Layout:
    Data bitmap: 270 - 270
    Inode bitmap: 286 - 286
    Inode Table: 5392 - 5901
    Data Blocks: 81921 - 90112
  Free Inodes: 2040 (100%)
  Free Blocks: 12 (0%)
  Total Directories: 0
  Stored Checksum: 0x1795

Group: 11:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 22441 - 24480
  Block Range: 90113 - 98304
  Layout:
    Data bitmap: 271 - 271
    Inode bitmap: 287 - 287
    Inode Table: 5902 - 6411
    Data Blocks: 90113 - 98304
  Free Inodes: 2040 (100%)
  Free Blocks: 1 (0%)
  Total Directories: 0
  Stored Checksum: 0x3E18

Group: 12:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 24481 - 26520
  Block Range: 98305 - 106496
  Layout:
    Data bitmap: 272 - 272
    Inode bitmap: 288 - 288
    Inode Table: 6412 - 6921
    Data Blocks: 98305 - 106496
  Free Inodes: 2040 (100%)
  Free Blocks: 4938 (60%)
  Total Directories: 0
  Stored Checksum: 0x5315

Group: 13:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 26521 - 28560
  Block Range: 106497 - 114688
  Layout:
    Data bitmap: 273 - 273
    Inode bitmap: 289 - 289
    Inode Table: 6922 - 7431
    Data Blocks: 106497 - 114688
  Free Inodes: 2040 (100%)
  Free Blocks: 1064 (12%)
  Total Directories: 0
  Stored Checksum: 0x47D9

Group: 14:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 28561 - 30600
  Block Range: 114689 - 122880
  Layout:
    Data bitmap: 274 - 274
    Inode bitmap: 290 - 290
    Inode Table: 7432 - 7941
    Data Blocks: 114689 - 122880
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x658D

Group: 15:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 30601 - 32640
  Block Range: 122881 - 131072
  Layout:
    Data bitmap: 275 - 275
    Inode bitmap: 291 - 291
    Inode Table: 8452 - 8961
    Data Blocks: 122881 - 131072
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x073A

Group: 16:
  Block Group Flags: [INODE_ZEROED] 
  Inode Range: 32641 - 34680
  Block Range: 131073 - 139264
  Layout:
    Data bitmap: 131073 - 131073
    Inode bitmap: 131082 - 131082
    Inode Table: 131091 - 131600
    Uninit Data Bitmaps: 131082 - 131088
    Uninit Inode Bitmaps: 131091 - 131097
    Uninit Inode Table: 135681 - 139250
    Data Blocks: 139265 - 139264
  Free Inodes: 1542 (75%)
  Free Blocks: 3476 (42%)
  Total Directories: 82
  Stored Checksum: 0x008E

Group: 17:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 34681 - 36720
  Block Range: 139265 - 147456
  Layout:
    Data bitmap: 131074 - 131074
    Inode bitmap: 131083 - 131083
    Inode Table: 131601 - 132110
    Data Blocks: 139265 - 147456
  Free Inodes: 2040 (100%)
  Free Blocks: 375 (4%)
  Total Directories: 0
  Stored Checksum: 0xD453

Group: 18:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 36721 - 38760
  Block Range: 147457 - 155648
  Layout:
    Data bitmap: 131075 - 131075
    Inode bitmap: 131084 - 131084
    Inode Table: 132111 - 132620
    Data Blocks: 147457 - 155648
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x3A49

Group: 19:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 38761 - 40800
  Block Range: 155649 - 163840
  Layout:
    Data bitmap: 131076 - 131076
    Inode bitmap: 131085 - 131085
    Inode Table: 132621 - 133130
    Data Blocks: 155649 - 163840
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0xFD9E

Group: 20:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 40801 - 42840
  Block Range: 163841 - 172032
  Layout:
    Data bitmap: 131077 - 131077
    Inode bitmap: 131086 - 131086
    Inode Table: 133131 - 133640
    Data Blocks: 163841 - 172032
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x983F

Group: 21:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 42841 - 44880
  Block Range: 172033 - 180224
  Layout:
    Data bitmap: 131078 - 131078
    Inode bitmap: 131087 - 131087
    Inode Table: 133641 - 134150
    Data Blocks: 172033 - 180224
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x9511

Group: 22:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 44881 - 46920
  Block Range: 180225 - 188416
  Layout:
    Data bitmap: 131079 - 131079
    Inode bitmap: 131088 - 131088
    Inode Table: 134151 - 134660
    Data Blocks: 180225 - 188416
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x27AF

Group: 23:
  Block Group Flags: [INODE_UNINIT, BLOCK_UNINIT, INODE_ZEROED] 
  Inode Range: 46921 - 48960
  Block Range: 188417 - 196608
  Layout:
    Data bitmap: 131080 - 131080
    Inode bitmap: 131089 - 131089
    Inode Table: 134661 - 135170
    Data Blocks: 188417 - 196608
  Free Inodes: 2040 (100%)
  Free Blocks: 8192 (100%)
  Total Directories: 0
  Stored Checksum: 0x037B

Group: 24:
  Block Group Flags: [INODE_UNINIT, INODE_ZEROED] 
  Inode Range: 48961 - 51000
  Block Range: 196609 - 203775
  Layout:
    Data bitmap: 131081 - 131081
    Inode bitmap: 131090 - 131090
    Inode Table: 135171 - 135680
    Data Blocks: 196609 - 203775
  Free Inodes: 2040 (100%)
  Free Blocks: 7167 (99%)
  Total Directories: 0
  Stored Checksum: 0xD763
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fls -o 411648  disk.flag.img 
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ fls -o 411648  disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ icat -o 411648 disk.flag.img 1876        
           -0.881573            34.311733
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ icat -o 411648 disk.flag.img 1872
nameserver 10.0.2.3
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ icat -o 411648 disk.flag.img 1876 > flag.txt

                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ ls
disk.flag.img  flag.txt
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ cat flag.txt  
           -0.881573            34.311733
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ icat -o 411648 disk.flag.img 1875           
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc

                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ ls
disk.flag.img  flag.txt  flag.txt.enc
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ openssl aes256 -d -salt -in flag.txt.enc -out flag_decrypted.txt -k unbreakablepassword1234567

*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40C719C0337F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ openssl aes256 -d -salt -in flag.txt.enc -out flag_decrypted.txt -k unbreakablepassword1234567


*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40F71E92947F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ ls
disk.flag.img  flag_decrypted.txt  flag.txt  flag.txt.enc
                                                                           
┌──(kali㉿kali)-[~/Downloads/OperatioOrchid]
└─$ cat flag_decrypted.txt 
picoCTF{h4un71ng_p457_1d02081e}           
'''

## Referencias


