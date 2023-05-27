# Mind your Ps and Qs

## Descripción

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)

## Pistas

Bits are expensive, I used only a little bit over 100 to save money

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/mindpqs]
└─$ wget https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values               
--2023-04-27 14:20:06--  https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 205 [application/octet-stream]
Saving to: ‘values’

values                               100%[======================================================================>]     205  --.-KB/s    in 0s      

2023-04-27 14:20:14 (368 MB/s) - ‘values’ saved [205/205]

                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/mindpqs]
└─$ cat values
Decrypt my super sick RSA:
c: 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n: 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e: 65537

C:\Users\Usuario>python3
Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()

C:\Users\Usuario>python3
Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from Cryoto.Util.number import inverse, long_to_bytes
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'Cryoto'
>>> from Crypto.Util.number import inverse, long_to_bytes
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> n = 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> p*q = n
  File "<stdin>", line 1
    p*q = n
    ^^^
SyntaxError: cannot assign to expression here. Maybe you meant '==' instead of '='?
>>> p*q == n
True
>>> e = 65537
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> tn = (p-1) * (q-1)
>>> d = inverse(e, tn)
>>> m = pow(c,d,n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
```

## Bandera

picoCTF{sma11_N_n0_g0od_73918962}

## Notas adicionales



## Referencias
- https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values