# Codebook

## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Pistas
1.- On the webshell, use `ls` to see if both files are in the directory you are in

2.- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
┌──(salimuga㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/3/code.py  
--2023-03-17 12:51:48--  https://artifacts.picoctf.net/c/3/code.py
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.17, 13.249.74.56, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.69]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1278 (1.2K) [application/octet-stream]
Grabando a: «code.py»

code.py             100%[================>]   1.25K  --.-KB/s    en 0s      

2023-03-17 12:51:49 (3.59 MB/s) - «code.py» guardado [1278/1278]

                                                                             
┌──(salimuga㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2023-03-17 12:52:10--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.17, 13.249.74.56, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.69]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 27 [application/octet-stream]
Grabando a: «codebook.txt»

codebook.txt        100%[================>]      27  --.-KB/s    en 0s      

2023-03-17 12:52:11 (14.2 MB/s) - «codebook.txt» guardado [27/27]
                                                                             
┌──(salimuga㉿kali)-[~]
└─$ python3 code.py 
picoCTF{c0d3b00k_455157_197a982c}

## Bandera

picoCTF{c0d3b00k_455157_197a982c}

## Notas adicionales


## Referencias
- https://artifacts.picoctf.net/c/3/code.py
- https://artifacts.picoctf.net/c/3/codebook.txt