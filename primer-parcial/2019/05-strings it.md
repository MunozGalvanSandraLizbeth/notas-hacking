# strings it

## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

## Pistas
[strings](https://linux.die.net/man/1/strings)

## Solución
Das clic derecho a la liga de file y pones copiar vinculo, una vez eso compilas los comandos ls -la para saber si lo tenemos guardado, después de eso notamos que es un archivo binario, por lo que se realiza lo siguiente

salimuga-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
salimuga-picoctf@webshell:~$ 

## Bandera

picoCTF{5tRIng5_1T_7f766a23}

## Notas adicionales


## Referencias
- https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
- https://linux.die.net/man/1/strings