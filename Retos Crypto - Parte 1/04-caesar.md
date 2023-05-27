# caesar

## Descripción

Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).

## Pistas

caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/cesar]
└─$ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
--2023-04-19 23:32:52--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext                           100%[======================================================================>]      35  --.-KB/s    in 0s      

2023-04-19 23:32:53 (44.4 MB/s) - ‘ciphertext’ saved [35/35]

                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/crypto/cesar]
└─$ cat ciphertext 
picoCTF{ynkooejcpdanqxeykjrbdofgkq}  

mport string
import re

abc=string.ascii_letters
encriptado = open ('ciphertext','r').read()
encriptado = re.findall('\{(.*?\}',encriptado)[0]

rot = 25
salida = ''
for car in encriptado:
	salida += abc [ (abc.find(car) + rot) % 26 ]
print(salida)

┌──(kali㉿kali)-[~/picoctf/crypto/cesar]
└─$ python3  exp.py.save
crossingtherubiconvfhsjkou
```

## Bandera

picoCTF{crossingtherubiconvfhsjkou}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext
- https://learncryptography.com/classical-encryption/caesar-cipher