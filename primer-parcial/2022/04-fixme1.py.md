# fixme1.py

## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/8/fixme1.py)

## Pistas
1.- Indentation is very meaningful in Python

2.- To view the file in the webshell, do: `$ nano fixme1.py`

3.- To exit `nano`, press Ctrl and x and follow the on-screen prompts.

4.- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
- En terminal de kali:
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 fixme1.py
  File "/home/salimuga/Descargas/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ sudo nano fixme1.py
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 fixme1.py  
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

- Dentro del nano fixme1.py:
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
print('That is correct! Here\'s your flag: ' + flag)

## Bandera

picoCTF{1nd3nt1ty_cr1515_182342f7}

## Notas adicionales
Para arreglar el error del código se tuvo que borrar el tabulador de la línea 20.

## Referencias
- https://artifacts.picoctf.net/c/8/fixme1.py