# Wave a flag

## Descripción
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information...

## Pistas
1.- This program will only work in the webshell or another Linux computer.

2.- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm`

3.- Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`

4.- -h and --help are the most common arguments to give to programs to get more information from them!

5.- Not every program implements help features like -h and --help.

## Solución
salimuga-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
--2023-03-15 18:18:31--  https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm.6'

warm.6                                                              100%[=================================================================================================================================================================>]  10.68K  --.-KB/s    in 0s      

2023-03-15 18:18:31 (282 MB/s) - 'warm.6' saved [10936/10936]

salimuga-picoctf@webshell:~$ ls
README.txt  flag  flagout.txt  strings  warm  warm.1  warm.2  warm.3  warm.4  warm.5  warm.6
salimuga-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
salimuga-picoctf@webshell:~$ strings warm | less

[2]+  Stopped                 strings warm | less

## Bandera

picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}

## Notas adicionales


## Referencias
https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm