# Level 13 - 14

## Objetivo
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on.

## Datos de acceso al nivel
Contraseña para el nivel 13: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Solución
---
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
...

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$ exit
logout
Connection to localhost closed.
bandit13@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

---
## Notas adicionales
ssh: Te conecta con el servidor remoto y te permite trabajar con él desde la línea de comandos.

## Referencias
https://desarrolloweb.com/articulos/guia-acceso-ssh-comandos-basicos-linux.html

