# Forbidden Paths

## Descripción
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55287/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Pistas
None

## Solución
Ingresa a la página, para este reto en el cuadro de texto debe ingresar el formato que te asigna el reto "/usr/share/nginx/html/" e ingresarle "flag.txt" al final del formato, para ingresar debemos de modificarlo para que nos de acceso, finalmente se debe acomodar de la forma "../../../../flag.txt" y presionar el botón "Read", finalmente te redireccionará a la contraseña del picoCTF.

## Bandera

picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}

## Notas adicionales


## Referencias
- http://saturn.picoctf.net:55287/