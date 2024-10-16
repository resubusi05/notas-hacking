# Retos picoCTF

# Level Milkslap

## Objetivo
Description
🥛

## Solucion
```
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ wget http://mercury.picoctf.net:48380/concat_v.png                   
--2024-10-14 12:17:57--  http://mercury.picoctf.net:48380/concat_v.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:48380... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png         12%[=>                ]   2.14M   187KB/s    in 11s     

2024-10-14 12:18:09 (192 KB/s) - Connection closed at byte 2244792. Retrying.

--2024-10-14 12:18:10--  (try: 2)  http://mercury.picoctf.net:48380/concat_v.png
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:48380... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png         54%[========>         ]   9.33M   276KB/s    in 17s     

2024-10-14 12:18:28 (553 KB/s) - Connection closed at byte 9783576. Retrying.

--2024-10-14 12:18:30--  (try: 3)  http://mercury.picoctf.net:48380/concat_v.png
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:48380... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png        100%[=================>]  17.26M   937KB/s    in 23s     

2024-10-14 12:18:53 (775 KB/s) - ‘concat_v.png’ saved [18095920/18095920]

                                                                              
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ binwalk concat_v.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
41            0x29            Zlib compressed data, default compression
3210141       0x30FB9D        MySQL ISAM compressed data file Version 2

                                                                              
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ binwalk concat_v.png extract

General Error: Cannot open file extract (CWD: /home/kali/Downloads/milkslap) : [Errno 2] No such file or directory: 'extract'

                                                                              
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ zsteg -v
zsteg: command not found
                                                                              
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ sudo gem install zsteg
[sudo] password for kali: 
Fetching iostruct-0.2.0.gem
Fetching zsteg-0.2.13.gem
Fetching rainbow-3.1.1.gem
Fetching zpng-0.4.5.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.2.0
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.2.0
Installing ri documentation for iostruct-0.2.0
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 1 seconds
4 gems installed
                                                                              
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ zsteg -a concat_v.png| grep pico
/var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:303:in `upto': stack level too deep (SystemStackError)
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:303:in `decoded_bytes'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
         ... 9483 levels...
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                              
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ export RUBY_THREAD_VM_STACK_SIZE=500000000
                                                                                                       
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ zsteg -a concat_v.png| grep pico          
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
/var/lib/gems/3.1.0/gems/iostruct-0.2.0/lib/iostruct.rb:167:in `inspect': stack level too deep (SystemStackError)
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.1.0/gems/iostruct-0.2.0/lib/iostruct.rb:167:in `inspect'
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.1.0/gems/iostruct-0.2.0/lib/iostruct.rb:167:in `inspect'
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.1.0/gems/iostruct-0.2.0/lib/iostruct.rb:167:in `inspect'
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s'
        from /var/lib/gems/3.1.0/gems/iostruct-0.2.0/lib/iostruct.rb:167:in `inspect'
         ... 4807703 levels...
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                       
┌──(kali㉿kali)-[~/Downloads/milkslap]
└─$ 

```

## Referencias


