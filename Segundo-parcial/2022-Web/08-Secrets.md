# Secrets

## Descripción
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:65352/).

## Pistas
folders folders folders

## Solución
Ingresa a la página, colocar al final del link "/secret/" y te redireccionará a esta página
![[Pasted image 20230505210225.png]]
dar clic derecho y dar en la opción "ver origen de página" y notarás que te da la opción de "hidden" y deberás colocarlo después de "/secret/" y te redireccionará a la siguiente página
![[Pasted image 20230505210617.png]]
y dar en la opción "ver origen de página", notarás que hay una línea "<input type"hidden" name"db" value"superhidden/xdfgwd.html">", lo cuál deberás colocar la palabra "/superhidden/" al final de lo anterior colocado, finalmente te dará la contraseña del picoCTF, pero en letras blancas, debes seleccionar para encontrarla.

## Bandera

picoCTF{succ3ss_@h3n1c@10n_790d2615}

## Notas adicionales


## Referencias
- http://saturn.picoctf.net:65352/