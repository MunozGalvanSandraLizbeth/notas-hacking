# Pixelated

## Descripción

I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png)

## Pistas

1.- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

2.- Think of different ways you can "stack" images

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]
└─$ wget https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png
--2023-04-27 14:37:43--  https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197172 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png                        100%[======================================================================>] 192.55K   287KB/s    in 0.7s    

2023-04-27 14:37:53 (287 KB/s) - ‘scrambled2.png’ saved [197172/197172]

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]
└─$ wget https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png
--2023-04-27 14:38:21--  https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197175 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png                        100%[======================================================================>] 192.55K   113KB/s    in 1.7s    

2023-04-27 14:38:32 (113 KB/s) - ‘scrambled1.png’ saved [197175/197175]

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flag.png
                                                                                    ┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]
└─$ open flag.png  
```

## Bandera

picoCTF{1b867c3e}

## Notas adicionales



## Referencias
- https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png
- https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png
- https://en.wikipedia.org/wiki/Visual_cryptography