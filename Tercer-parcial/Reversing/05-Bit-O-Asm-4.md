# Bit-O-Asm-4

## Descripción

Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Pistas

1.- Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.

2.- Of course, if you're really good, you'll only need one attempt to solve this problem.

## Solución

```
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
```

## Bandera

picoCTF{654773}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt