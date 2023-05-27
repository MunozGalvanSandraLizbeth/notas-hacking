# Glory of the Garden

## Descripción

This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

## Pistas

What is a hex editor?

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ wget https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
--2023-03-23 14:09:05--  https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg                       100%[========================================================>]   2.19M   559KB/s    in 4.4s    

2023-03-23 14:09:10 (510 KB/s) - ‘garden.jpg’ saved [2295192/2295192]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ ls
garden.jpg
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ file garden.jpg 
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ open garden.jpg 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ 
** (ristretto:4788): WARNING **: 14:10:46.107: (file.c:619):rstto_file_get_thumbnail: code should not be reached

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ hexeditor garden.jpg 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/glory]
└─$ strings garden.jpg -n 20 | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
```

## Bandera

picoCTF{more_than_m33ts_the_3y3eBdBd2cc}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg