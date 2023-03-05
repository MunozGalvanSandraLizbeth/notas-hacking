# Level 25 - 26

## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Datos de acceso al nivel
Contraseña para el nivel : p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución
---
bandit25@bandit:~$ bandit25@bandit:~$ ls
bandit26.sshkey
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220



  Enjoy your stay!
Connection to localhost closed.
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220
  Enjoy your stay!

c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                      Vim: Caught deadly signal HUP                                                                         1,1           All
Vim: Finished.
Connection to localhost closed.
bandit25@bandit:~$ :

---
## Notas adicionales
No fue fácil, no entendía al principio, me guíe de un video

## Referencias
https://www.youtube.com/watch?v=fTOedf5Y91I

