# Vigenere

## Descripción

Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".

## Pistas

https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

## Solución

```
┌──(kali㉿kali)-[~/picoctf/3erparcial/vigenere]
└─$ wget https://artifacts.picoctf.net/c/160/cipher.txt 
--2023-05-20 20:53:35--  https://artifacts.picoctf.net/c/160/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.103, 18.154.144.85, 18.154.144.104, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.103|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt               100%[===============================>]      43  --.-KB/s    in 0s      

2023-05-20 20:53:35 (105 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                 
┌──(kali㉿kali)-[~/picoctf/3erparcial/vigenere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}
```

## Bandera

picoCTF{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/159/cipher.txt
- https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher