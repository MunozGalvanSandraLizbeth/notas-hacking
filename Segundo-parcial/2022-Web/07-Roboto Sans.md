# Roboto Sans

## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:61304/) out.

## Pistas
None

## Solución
ingresar a la página, dar clic al link de la página y agregarle /robots.txt y recargar, te llevará a una página donde te da códigos en base 64, copear únicamente esta línea "anMvbXlmaWxlLnR4dA=" y pegarla en el convertidor de base 64 anexado en referencias, una vez decodificado se debe copear el resultado decodificado y remplazarlo en vez de "robots.txt" en el link antes modificado, finalmente te dará la contraseña del picoCTF.

## Bandera

picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}

## Notas adicionales


## Referencias
- http://saturn.picoctf.net:61304/
- [Base64 Decode and Encode - Online](https://www.base64decode.org/)