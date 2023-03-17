# PW Crack 1

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/27/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/27/level1.flag.txt.enc) in the same directory too.

## Pistas
1.- To view the file in the webshell, do: `$ nano level1.py`

2.- To exit `nano`, press Ctrl and x and follow the on-screen prompts.

3.- The `str_xor` function does not need to be reverse engineered for this challenge.
[[07-PW Crack 1]]
## Solución
- Dentro de la terminal de kali:
┌──(salimuga㉿kali)-[~/Descargas]
└─$ sudo nano level1.py
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level1.py            
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}

- Dentro del nano level1.py:
 THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT #####################>
def str_xor(secret, key):
    extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_ke>
############################################################################>


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "691d"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return

## Bandera

picoCTF{545h_r1ng1ng_56891419}

## Notas adicionales
Encuentras la clave que te piden dentro del nano.

## Referencias
- https://artifacts.picoctf.net/c/27/level1.py
- https://artifacts.picoctf.net/c/27/level1.flag.txt.enc