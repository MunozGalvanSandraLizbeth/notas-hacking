# Easy1

## Descripción

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

## Pistas

1.- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{HELLO}' as the flag.

2.- Please use all caps for the message.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/easy1]
└─$ wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt      
--2023-04-19 23:12:18--  https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1571 (1.5K) [application/octet-stream]
Saving to: ‘table.txt’

table.txt                            100%[======================================================================>]   1.53K  --.-KB/s    in 0s      

2023-04-19 23:12:18 (38.8 MB/s) - ‘table.txt’ saved [1571/1571]

                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/easy1]
└─$ open table.txt 
```

## Bandera

picoCTF{CRYPTOISFUN}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt