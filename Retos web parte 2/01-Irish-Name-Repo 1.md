# Irish-Name-Repo 1

## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

## Pistas
1.- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

2.-Try to think about how the website verifies your login.

## Solución
Se lee la conversación de support, luego nos vamos a la área de inicia sesión, intentamos poner un usuario y contraseña al azar, luego vemos el código fuente en Inspeccionar, y tenemos que consultar la página anexada para consultar las inyecciones SQL, después de entender vamos a ingresar nuevamente 

## Bandera

picoCTF{s0m3_SQL_c218b685}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/problem/39720/login.html
- https://jupiter.challenges.picoctf.org/problem/39720/