# Level x

## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data.

## Datos de acceso al nivel
Contraseña para el nivel 10: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
---
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ echo "hola mundo"
hola mundo
bandit10@bandit:~$ echo "hola mundo" | base64
aG9sYSBtdW5kbwo=
bandit10@bandit:~$ echo -n aG9sYSBtdW5kbwo= | base64 -d
hola mundo
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

---
## Notas adicionales
echo: 

## Referencias


