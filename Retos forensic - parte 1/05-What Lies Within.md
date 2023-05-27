# What Lies Within

## Descripción

There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Pistas

There is data encoded somewhere... there might be an online decoder.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/whatlieswithin]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2023-03-24 22:37:56--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                    100%[========================================================>] 610.57K  14.0KB/s    in 48s     

2023-03-24 22:38:47 (12.6 KB/s) - ‘buildings.png’ saved [625219/625219]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/whatlieswithin]
└─$ open buildings.png 
┌──(kali㉿kali)-[~/picoctf/whatlieswithin]
└─$ zsteg -a buildings.png 
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b3p,r,msb,xy        .. text: "R\t\t\t\t\t\tII\t[[[["
b3p,g,lsb,xy        .. text: "\n\nJJJJ\nJP"
b3p,g,msb,xy        .. text: "RRRR\t\t\tY["
┌──(kali㉿kali)-[~/picoctf/whatlieswithin]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```

## Bandera

picoCTF{h1d1ng_1n_th3_b1t5}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png