# Level 14 - 15

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso al nivel
Contraseña para el nivel 14: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución
---
bandit14@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Feb 21 22:02 .
drwxr-xr-x 70 root root 4096 Feb 21 22:04 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
drwxr-xr-x  2 root root 4096 Feb 21 22:02 .ssh
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$

---
## Notas adicionales
nc: Lee y escribe datos a través de redes, desde la línea de comandos.
Otras de sus funciones:
 1. Ver si un puerto esta en uso
 2. Conexión a un sistema remoto
 3. Conexiones a puertos UDP
 4. Ncat como proxy
 5. Copia ficheros
 6. Crea una puerta trasera
 7. Redirección de puertos

## Referencias
https://www.ochobitshacenunbyte.com/2021/11/04/uso-del-comando-ncat-nc-en-linux-con-ejemplos/

