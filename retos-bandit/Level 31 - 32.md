# Level 31 - 32

## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
Contraseña para el nivel 31: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solución
---
bandit31@bandit:~$ mkdir /tmp/sandy
mkdir: cannot create directory ‘/tmp/sandy’: File exists
bandit31@bandit:~$ mkdir /tmp/sandybandit31
bandit31@bandit:~$ cd /tmp/sandybandit31
bandit31@bandit:/tmp/sandybandit31$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), 382 bytes | 382.00 KiB/s, done.
bandit31@bandit:/tmp/sandybandit31$ ls
repo
bandit31@bandit:/tmp/sandybandit31$ cd repo/
bandit31@bandit:/tmp/sandybandit31/repo$ ls
README.md
bandit31@bandit:/tmp/sandybandit31/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/sandybandit31/repo$ ls
README.md
bandit31@bandit:/tmp/sandybandit31/repo$ nano key.txt
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit31@bandit:/tmp/sandybandit31/repo$ ls
README.md
bandit31@bandit:/tmp/sandybandit31/repo$ nano key.txt
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit31@bandit:/tmp/sandybandit31/repo$ ls
key.txt  README.md
bandit31@bandit:/tmp/sandybandit31/repo$ git add key.txt
The following paths are ignored by one of your .gitignore files:
key.txt
hint: Use -f if you really want to add them.
hint: Turn this message off by running
hint: "git config advice.addIgnoredFile false"
bandit31@bandit:/tmp/sandybandit31/repo$ ls -a
.  ..  .git  .gitignore  key.txt  README.md
bandit31@bandit:/tmp/sandybandit31/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/sandybandit31/repo$ rm .gitignore
bandit31@bandit:/tmp/sandybandit31/repo$ git add key.txt
bandit31@bandit:/tmp/sandybandit31/repo$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   key.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    .gitignore

bandit31@bandit:/tmp/sandybandit31/repo$ git commit -m "a ver que sale"
[master 88242cf] a ver que sale
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/sandybandit31/repo$ git log
commit 88242cfc9051622da5eeff6129f9f9046f81175e (HEAD -> master)
Author: bandit31 <bandit31@overthewire.org>
Date:   Mon Mar 6 01:26:49 2023 +0000

    a ver que sale

commit 5c1d06a02163d3224e06f00ca0bbfe1c2768ce00 (origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:14 2023 +0000

    initial commit
bandit31@bandit:/tmp/sandybandit31/repo$ git push
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
bandit31-git@localhost's password:
Permission denied, please try again.
bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 324 bytes | 324.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'

---
# Notas adicionales


# Referencias


