# Flags

## Descripción

What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

## Pistas

The flag is in the format PICOCTF{}

## Solución

```
┌──(kali㉿kali)-[~/…/3erparcial/binaryexplotation/crypto/flags]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
--2023-05-20 16:12:07--  https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43257 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                 100%[===============================>]  42.24K  --.-KB/s    in 0.006s  

2023-05-20 16:12:07 (6.92 MB/s) - ‘flag.png’ saved [43257/43257]

                                                                                                 
┌──(kali㉿kali)-[~/…/3erparcial/binaryexplotation/crypto/flags]
└─$ open flag.png        
                                                                                                 
┌──(kali㉿kali)-[~/…/3erparcial/binaryexplotation/crypto/flags]
└─$ 
** (ristretto:13073): WARNING **: 16:12:13.037: (file.c:619):rstto_file_get_thumbnail: code should not be reached
```

## Bandera

picoCTF{F1AG5AND5TUFF}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png