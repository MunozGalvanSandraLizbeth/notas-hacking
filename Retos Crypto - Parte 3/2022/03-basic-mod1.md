# basic-mod1

## Descripción

We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas

1.- Do you know what `mod 37` means?

2.- `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ wget https://artifacts.picoctf.net/c/128/message.txt                                   
--2023-05-02 19:47:49--  https://artifacts.picoctf.net/c/128/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.32, 18.154.132.74, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 84 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                     100%[======================================================================================================>]      84  --.-KB/s    in 0s      

2023-05-02 19:47:58 (478 KB/s) - ‘message.txt’ saved [84/84]

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ cat message.txt 
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138                                                                                                                                                                                                
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ nano  exp.py 
datos = open('message.txt').read().split()

print (datos)

flag = ''

for n in datos:
     c = int(n) % 37
     if c>=0 and c <=25:
        s = chr(c+65)
     elif c >= 25 and c <= 35:
        s = chr(c+22)
     else:
        s = '_'
     flag += s
print(f"picoCTF{{{flag}}}")
                                                                                        ┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]
└─$ python3 exp.py 
['165', '248', '94', '346', '299', '73', '198', '221', '313', '137', '205', '87', '336', '110', '186', '69', '223', '213', '216', '216', '177', '138']
picoCTF{R0UND_N_R0UND_B6B25531}
```

## Bandera

picoCTF{R0UND_N_R0UND_B6B25531}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/129/message.txt