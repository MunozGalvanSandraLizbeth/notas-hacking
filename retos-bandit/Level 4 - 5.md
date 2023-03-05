# Level 4 - 5

## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso al nivel
Contraseña para el nivel 4: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Solución
---
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./-file00
=MÐEWfbandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: Non-ISO extended-ASCII text, with NEL line terminators
./-file06: Non-ISO extended-ASCII text, with no line terminators, with escape sequences
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./file07
cat: ./file07: No such file or directory
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

---
## Notas adicionales
cat /file: Muestra el contenido del archivo
file: permite **detectar el tipo** y **formato** de **un archivo**

## Referencias


