# transposition-trial

## Descripción

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/192/message.txt).

## Pistas

Split the message up into blocks of 3 and see how the first block is scrambled

## Solución

```
┌──(kali㉿kali)-[~/picoctf/3erparcial]
└─$ wget https://artifacts.picoctf.net/c/191/message.txt
--2023-05-20 20:42:14--  https://artifacts.picoctf.net/c/191/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.107, 18.154.144.85, 18.154.144.103, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.107|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt              100%[===============================>]      54  --.-KB/s    in 0s      

2023-05-20 20:42:15 (90.0 MB/s) - ‘message.txt’ saved [54/54]

                                                                                                 
┌──(kali㉿kali)-[~/picoctf/3erparcial]
└─$ cat message.txt  
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4                                                                                                 

┌──(kali㉿kali)-[~/picoctf/3erparcial]
└─$ nano message.py

flag_enc = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4"

flag = ""
for i in range(12, len(flag_enc),3):
    temp = flag_enc[i:i+3]
    flag += temp[2] + temp[0:2]

print(flag)

   
┌──(kali㉿kali)-[~/picoctf/3erparcial]
└─$ python3 message.py                                                        
picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}
```

## Bandera

picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/192/message.txt