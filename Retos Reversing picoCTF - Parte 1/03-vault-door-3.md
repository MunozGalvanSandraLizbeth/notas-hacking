# vault-door-3

## Descripción

This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java)

## Pistas

Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.

## Solución

```
allow pasting
Uncaught SyntaxError: unexpected token: identifier
var password = "jU5t_a_sna_3lpm18g947_u_4_m9r54f"
undefined
var buffer = Array(32);
undefined
> for (i=0; i<8; i++) {
        buffer[i] = password.charAt(i);
}                                                                                                              for (; i<16; i++){
    buffer[1] = password.charAt(23-1);..****
```

## Bandera

picoCTF{jU5t_a_sna_3lpm18g947_u_4_m9r54f}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java