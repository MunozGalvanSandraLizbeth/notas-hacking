# Level 3 - 4

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos de acceso al nivel
Contraseña para el nivel 3: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solución
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Feb 21 22:03 .
drwxr-xr-x 3 root    root    4096 Feb 21 22:03 ..
-rw-r----- 1 bandit4 bandit3   33 Feb 21 22:03 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Notas adicionales
cd/: Cambia al directorio raíz 
ls -la: Lista archivos con formato, incluye archivos ocultos

## Referencias


