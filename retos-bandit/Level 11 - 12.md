# Level x

## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Datos de acceso al nivel
Contraseña para el nivel 11: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
---
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ man tr
bandit11@bandit:~$ bandit11@bandit:~$ cat data.txt | tr a-zA-Z n-za-mN-ZA-M
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

---
## Notas adicionales
tr: Traduce, elimina y comprime caracteres de la entrada estándar y escribe el resultado en la salida estándar.

## Referencias
https://www.linuxjournal.com/article/2563

