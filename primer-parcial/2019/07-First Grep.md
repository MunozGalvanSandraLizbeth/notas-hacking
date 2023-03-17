# First Grep

## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución
salimuga㉿kali)-[~]
└─$ ls          
Descargas   Escritorio  Música      Público
Documentos  Imágenes    Plantillas  Vídeos
                                                                             
┌──(salimuga㉿kali)-[~]
└─$ cd Descargas
                                                                             
┌──(salimuga㉿kali)-[~/Descargas]
└─$ cat file | grep pico
picoCTF{grep_is_good_to_find_things_5af9d829}

## Bandera

picoCTF{grep_is_good_to_find_things_5af9d829}

## Notas adicionales


## Referencias
- https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
- https://ryanstutorials.net/linuxtutorial/grep.php