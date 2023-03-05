# Level 27 - 28

## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
Contraseña para el nivel : YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución
---
bandit27@bandit:~$ mktemp -d
/tmp/tmp.rgEH0NetcS
bandit27@bandit:~$ cd /tmp/tmp.rgEH0NetcS
bandit27@bandit:/tmp/tmp.rgEH0NetcS$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.rgEH0NetcS$ ls -la
total 124
drwx------    3 bandit27 bandit27   4096 Mar  5 23:34 .
drwxrwx-wt 1131 root     root     114688 Mar  5 23:35 ..
drwxrwxr-x    3 bandit27 bandit27   4096 Mar  5 23:35 repo
bandit27@bandit:/tmp/tmp.rgEH0NetcS$ ls
repo
bandit27@bandit:/tmp/tmp.rgEH0NetcS$ cat repo
cat: repo: Is a directory
bandit27@bandit:/tmp/tmp.rgEH0NetcS$ cat README
cat: README: No such file or directory
bandit27@bandit:/tmp/tmp.rgEH0NetcS$ cd repo
bandit27@bandit:/tmp/tmp.rgEH0NetcS/repo$ ls
README
bandit27@bandit:/tmp/tmp.rgEH0NetcS/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/tmp.rgEH0NetcS/repo$

---
## Notas adicionales
mktemp: permite a los usuarios crear un archivo o directorio temporal.

## Referencias
https://howtoforge.es/tutorial-del-comando-mktemp-de-linux-para-principiantes-5-ejemplos/

