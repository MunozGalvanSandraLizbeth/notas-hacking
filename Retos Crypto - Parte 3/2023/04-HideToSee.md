# HideToSee

## Descripción

How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).

## Pistas

Download the image and try to extract it.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/hidetosee]
└─$ 
└─$ wget https://artifacts.picoctf.net/c/237/atbash.jpg 
}--2023-05-02 21:18:28--  https://artifacts.picoctf.net/c/237/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.108, 18.154.132.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51508 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                                      100%[======================================================================================================>]  50.30K  --.-KB/s    in 0.1s    

2023-05-02 21:18:37 (504 KB/s) - ‘atbash.jpg’ saved [51508/51508]

                                                                                        ┌──(kali㉿kali)-[~/picoctf/crypto/hidetosee]
└─$ open atbash.jpg
```

## Bandera

picoCTF{atbash_crack_05b2a65a}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/235/atbash.jpg