# GDB baby step 1

## Descripción

Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

## Pistas

1.- gdb is a very good debugger to use for this problem and many others!

2.- `main` is actually a recognized symbol that can be used with gdb commands.

## Solución

Se desensambla el código proporcionado, recibirás 0x86342, que en decimal seria 549698

```
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep1]
└─$ chmod +x debugger0_a 
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep1]
└─$ gdb debugger0_a -q
GEF for linux ready, type `gef' to start, `gef config' to configure
88 commands loaded and 5 functions added for GDB 13.1 in 0.00ms using Python engine 3.11
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
gef➤  disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   rbp
   0x000000000000112e <+5>:     mov    rbp,rsp
   0x0000000000001131 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000001134 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000001138 <+15>:    mov    eax,0x86342
   0x000000000000113d <+20>:    pop    rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
gef➤  quit
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep1]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x86342)
549698
>>> exit()
```

## Bandera

picoCTF{549698}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/512/debugger0_a