# PW Crack 2

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/29/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/29/level2.flag.txt.enc) in the same directory too.

## Pistas
1.- Does that encoding look familiar?

2.- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
- Dentro de la terminal de kali:
┌──(salimuga㉿kali)-[~/Descargas]
└─$ sudo nano level2.py
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3            
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
39ce
>>> exit()
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level2.py  
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}

- Dentro del nano level2.py:
THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT #####################>
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_ke>
############################################################################>

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")

## Bandera

picoCTF{tr45h_51ng1ng_502ec42e}

## Notas adicionales
Se tiene que hacer una conversión con python3.

### Comando    descripción


## Referencias
- https://artifacts.picoctf.net/c/29/level2.py
- https://artifacts.picoctf.net/c/29/level2.flag.txt.enc