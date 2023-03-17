# PW Crack 3

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/33/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/33/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/33/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas
1.- To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`

2.- To exit `bvi` type `:q` and press enter.

3.- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
- Dentro de la terminal de kali:
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 6997
That password is incorrect
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 3ac8
That password is incorrect
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: f0ac
That password is incorrect
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 4b17
That password is incorrect
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: ec27
That password is incorrect
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 4e66
That password is incorrect
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}

- Dentro del nano level3.py:
pw crack 3:
def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


The strings below are 7 possibilities for the correct password. 
(Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

## Bandera

picoCTF{m45h_fl1ng1ng_2b072a90}

## Notas adicionales
Se tuvieron que usar todas las claves hasta dar con la correcta.

## Referencias
- https://artifacts.picoctf.net/c/33/level3.py
- https://artifacts.picoctf.net/c/33/level3.flag.txt.enc
- https://artifacts.picoctf.net/c/33/level3.hash.bin