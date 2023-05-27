# The Numbers

## Descripción

The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Pistas

The flag is in the format PICOCTF{}

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/thenumbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png 
--2023-04-19 22:52:51--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png                      100%[======================================================================>]  98.36K  --.-KB/s    in 0.1s    

2023-04-19 22:52:52 (671 KB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/thenumbers]
└─$ ls
the_numbers.png
                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/thenumbers]
└─$ file the_numbers.png        
the_numbers.png: PNG image data, 774 x 433, 8-bit/color RGB, non-interlaced
                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/thenumbers]
└─$ open the_numbers.png 
16 9 3 15 3 20 6 {20 8 5 14 21 13 2 5 18 19 13 1 19 15 14}
picoctfthenumbersmason
```

## Bandera

picoCTF{thenumbersmason}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png