# Level 23 - 24

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel
Contraseña para el nivel 23: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución
---
bandit23@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Feb 21 22:02 .
drwxr-xr-x 70 root root 4096 Feb 21 22:04 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit23@bandit:~$  ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mkdir /tmp/kd
mkdir: cannot create directory ‘/tmp/kd’: File exists
bandit23@bandit:~$ ~$
~$: command not found
bandit23@bandit:~$
bandit23@bandit:~$ mkdir /tmp/kd
mkdir: cannot create directory ‘/tmp/kd’: File exists
bandit23@bandit:~$ cd /tmp/kd
bandit23@bandit:/tmp/kd$ echo "cat /etc/bandit_pass/bandit24 >
> /tmp/kd/password" > script.sh
bandit23@bandit:/tmp/kd$ cat script.sh
cat /etc/bandit_pass/bandit24 >
/tmp/kd/password
bandit23@bandit:/tmp/kd$ chmod +x script.sh
bandit23@bandit:/tmp/kd$ touch password
bandit23@bandit:/tmp/kd$ chmod 666 password
bandit23@bandit:/tmp/kd$ ls -la
total 124
drwxrwxr-x    2 bandit23 bandit23   4096 Mar  4 21:28 .
drwxrwx-wt 1032 root     root     114688 Mar  5 21:22 ..
-rw-rw-rw-    1 bandit23 bandit23      0 Mar  5 21:22 password
-rwxrwxr-x    1 bandit23 bandit23     50 Mar  5 21:21 script.sh
bandit23@bandit:/tmp/kd$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/kd$ ls -la
total 124
drwxrwxr-x    2 bandit23 bandit23   4096 Mar  4 21:28 .
drwxrwx-wt 1032 root     root     114688 Mar  5 21:23 ..
-rw-rw-rw-    1 bandit23 bandit23      0 Mar  5 21:22 password
-rwxrwxr-x    1 bandit23 bandit23     50 Mar  5 21:21 script.sh
bandit23@bandit:/tmp/kd$ date
Sun Mar  5 09:23:05 PM UTC 2023
bandit23@bandit:/tmp/kd$ ls -la
total 124
drwxrwxr-x    2 bandit23 bandit23   4096 Mar  4 21:28 .
drwxrwx-wt 1032 root     root     114688 Mar  5 21:23 ..
-rw-rw-rw-    1 bandit23 bandit23      0 Mar  5 21:22 password
-rwxrwxr-x    1 bandit23 bandit23     50 Mar  5 21:21 script.sh
bandit23@bandit:/tmp/kd$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

---
## Notas adicionales
mkdir:
chmod:
touch:

## Referencias


