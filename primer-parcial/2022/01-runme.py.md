# runme.py

## Descripción
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/13/runme.py)

## Pistas
1.- If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.

2.- To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'

3.- Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!

4.- Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 runme.py` You should have the flag now!

## Solución
Solución 1:
┌──(salimuga㉿kali)-[~]
└─$ wget
wget: falta la URL
Modo de empleo: wget [OPCIÓN]... [URL]...

Pruebe `wget --help' para ver más opciones.
                                                                             
┌──(salimuga㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/34/runme.py
--2023-03-17 12:01:08--  https://artifacts.picoctf.net/c/34/runme.py
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.17, 13.249.74.69, 13.249.74.56, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.17]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 270 [application/octet-stream]
Grabando a: «runme.py»

runme.py            100%[================>]     270  --.-KB/s    en 0s      

2023-03-17 12:01:09 (158 MB/s) - «runme.py» guardado [270/270]

                                                                             
┌──(salimuga㉿kali)-[~]
└─$ python3 runme.py
picoCTF{run_s4n1ty_run}

Solución 2: 
Simplemente abrir el archivo descargado y te da la contraseña directamente.

## Bandera

picoCTF{run_s4n1ty_run}

## Notas adicionales


## Referencias
- https://artifacts.picoctf.net/c/13/runme.py