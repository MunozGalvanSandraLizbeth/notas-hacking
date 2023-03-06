# Level 29 - 30

## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
Contraseña para el nivel 29: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución
---
bandit29@bandit:~$ mkdir /tmp/sandy
bandit29@bandit:~$ cd /tmp/sandy
bandit29@bandit:/tmp/sandy$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/sandy$ ls
repo
bandit29@bandit:/tmp/sandy$ ca
ca: command not found
bandit29@bandit:/tmp/sandy$ ls -la
total 124
drwxrwxr-x    3 bandit29 bandit29   4096 Mar  6 00:23 .
drwxrwx-wt 1153 root     root     114688 Mar  6 00:26 ..
drwxrwxr-x    3 bandit29 bandit29   4096 Mar  6 00:25 repo
bandit29@bandit:/tmp/sandy$ cd repo/
bandit29@bandit:/tmp/sandy/repo$ ls
README.md
bandit29@bandit:/tmp/sandy/repo$ cat README.md
Bandit Notes
Some notes for bandit30 of bandit.
credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/sandy/repo$ git log
commit 0afe3501277395fbfa017480925edee3df6e8bb5 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    fix username

commit c2606dfc0aef7179bf1ccd6cffa9ed19151facb4
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/sandy/repo$ git diff 0afe3501277395fbfa017480925edee3df6e8bb5
bandit29@bandit:/tmp/sandy/repo$ git diff 0afe3501277395fbfa017480925edee3df6e8bb5 c2606dfc0aef7179bf1ccd6cffa9ed19151facb4
diff --git a/README.md b/README.md
index 1af21d3..2da2f39 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.

 ## credentials

-- username: bandit30
+- username: bandit29
 - password: <no passwords in production!>

bandit29@bandit:/tmp/sandy/repo$ git branch
* master
bandit29@bandit:/tmp/sandy/repo$ git show-branch -a
 [master] fix username
 ! [origin/HEAD] fix username
  ! [origin/dev] add data needed for development
   ! [origin/master] fix username
    ! [origin/sploits-dev] add some silly exploit, just for shit and giggles
-----
    + [origin/sploits-dev] add some silly exploit, just for shit and giggles
  +   [origin/dev] add data needed for development
  +   [origin/dev^] add gif2ascii
*++++ [master] fix username
bandit29@bandit:/tmp/sandy/repo$ git remote origin
error: Unknown subcommand: origin
usage: git remote [-v | --verbose]
   or: git remote add [-t <branch>] [-m <master>] [-f] [--tags | --no-tags] [--mirror=<fetch|push>] <name> <url>
   or: git remote rename <old> <new>
   or: git remote remove <name>
   or: git remote set-head <name> (-a | --auto | -d | --delete | <branch>)
   or: git remote [-v | --verbose] show [-n] <name>
   or: git remote prune [-n | --dry-run] <name>
   or: git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)...]
   or: git remote set-branches [--add] <name> <branch>...
   or: git remote get-url [--push] [--all] <name>
   or: git remote set-url [--push] <name> <newurl> [<oldurl>]
   or: git remote set-url --add <name> <newurl>
   or: git remote set-url --delete <name> <url>

    -v, --verbose         be verbose; must be placed before a subcommand

bandit29@bandit:/tmp/sandy/repo$ git remote show origin
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
bandit29-git@localhost's password: 
remote origin
  Fetch URL: ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
  Push  URL: ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
  HEAD branch: master
  Remote branches:
    dev         tracked
    master      tracked
    sploits-dev tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)
bandit29@bandit:/tmp/sandy/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/sandy/repo$ ls
code  README.md
bandit29@bandit:/tmp/sandy/repo$ cat README.md
Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

# Notas adicionales


# Referencias


