# Reto

## Descripción

This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or [http://jupiter.challenges.picoctf.org:50522](http://jupiter.challenges.picoctf.org:50522/)

## Pistas

You don't need to download a new web browser

## Solución

```
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/50522/flag -H "User-Agent: picobrowser" | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}</code></p>
```

## Bandera

picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/problem/50522/
- http://jupiter.challenges.picoctf.org:50522/