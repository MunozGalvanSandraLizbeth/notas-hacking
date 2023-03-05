# Level 7 - 8

## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso al nivel
Contraseña para el nivel 7: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución
---
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP

---
## Notas adicionales
wc: permite contar el número de líneas, palabras, caracteres y bytes de cada archivo o entrada estándar e imprimir el resultado.

grep: Busca un patrón que definamos en un archivo de texto.

## Referencias
https://noviello.it/es/como-usar-el-comando-wc-count-number-word-characters-en-linux/
www.hostinger.es/tutoriales/comando-grep-linux

