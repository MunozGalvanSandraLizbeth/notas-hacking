# extensions

## Descripción

This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Pistas

1.- How do operating systems know what kind of file it is? (It's not just the ending!

2.- Make sure to submit the flag as picoCTF{XXXXX}

## Solución

```
──(kali㉿kali)-[~/picoctf]
└─$ mkdir extensions  
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf]
└─$ cd extensions 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt    
--2023-03-23 14:36:17--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt                         100%[========================================================>]   9.75K  --.-KB/s    in 0s      

2023-03-23 14:36:18 (143 MB/s) - ‘flag.txt’ saved [9984/9984]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ ls  
flag.txt
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ ls -l
total 12
-rw-r--r-- 1 kali kali 9984 Oct 26  2020 flag.txt
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ xxd -l 32 flag.txt
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ mv flag.txt flag.png
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/extensions]
└─$ open flag.png 
```

## Bandera

picoCTF{now_you_know_about_extensions}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt