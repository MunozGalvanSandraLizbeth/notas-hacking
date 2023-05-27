# GET aHEAD

## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:34561/](http://mercury.picoctf.net:34561/)


## Pistas

1.- Maybe you have more than 2 choices.

2.- Check out tools like Burpsuite to modify your requests and look at the responses

## Solución

```
Content-type
	text/html; charset=UTF-8
flag
	picoCTF{r3j3ct_th3_du4l1ty_6ef27873}

──(kali㉿kali)-[~]
└─$ curl -I http://mercury.picoctf.net:21939/index.php
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_5of16955}
```

## Bandera

picoCTF{r3j3ct_th3_du4l1ty_5of16955}

## Notas adicionales



## Referencias
- http://mercury.picoctf.net:34561/ 