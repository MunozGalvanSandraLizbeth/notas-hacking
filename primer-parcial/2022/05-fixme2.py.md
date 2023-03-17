# fixme2.py

## Descripción
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/11/fixme2.py)

## Pistas
1.- Are equality and assignment the same symbol?

2.- To view the file in the webshell, do: `$ nano fixme2.py`

3.- To exit `nano`, press Ctrl and x and follow the on-screen prompts.

4.- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
- En la terminal de kali:
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 fixme2.py  
  File "/home/salimuga/Descargas/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ sudo nano fixme2.py
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 fixme2.py  
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}

- Dentro del nano fixme2.py: 
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_ke>


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0>

  
flag = str_xor(flag_enc, 'enkidu')

 Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')

## Bandera

picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}

## Notas adicionales
Para arreglar el error, se agregó un = faltante en la línea 22.

## Referencias
- https://artifacts.picoctf.net/c/11/fixme2.py