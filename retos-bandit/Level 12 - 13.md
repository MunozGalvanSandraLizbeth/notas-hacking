# Level 12 - 13

## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso al nivel
Contraseña para el nivel 12: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solución
---
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cat data.txt
00000000: 1f8b 0808 8c3f f563 0203 6461 7461 322e  .....?.c..data2.
00000010: 6269 6e00 0134 02cb fd42 5a68 3931 4159  bin..4...BZh91AY
00000020: 2653 5953 6696 8100 001b 7fff fbdb effb  &SYSf...........
00000030: b41f 6efa a7cb ebee fff3 b7ad 897d f77f  ..n..........}..
00000040: 67bf beff bb6b aaff ff3b ff7b b001 3b5b  g....k...;.{..;[
00000050: 4100 00d0 3101 881a 0d34 01a0 000d 0006  A...1....4......
00000060: 10c4 d006 41b5 1a0d 0064 0340 64c8 3468  ....A....d.@d.4h
00000070: 1934 1a0d 1a68 da26 26d3 50e4 d0d3 40d0  .4...h.&&.P...@.
00000080: d001 a341 b500 0032 320d 0323 47a9 a683  ...A...22..#G...
00000090: 4346 9a00 3d40 36a0 0308 184d 0640 0068  CF..=@6....M.@.h
000000a0: 0c43 466a 0d34 6832 9a68 6430 40d3 4d34  .CFj.4h2.hd0@.M4
000000b0: d0d0 7a80 d0c2 69a3 268d 1a06 81a0 00d0  ..z...i.&.......
000000c0: c83f 5232 3400 c406 8da8 0680 3400 6800  .?R24.......4.h.
000000d0: 001a 0020 2823 e282 2299 1ae9 cfa4 8ea0  ... (#..".......
000000e0: 716d 6e03 9844 dd8b 7260 8c1e e05c d068  qmn..D..r`...\.h
000000f0: 9a86 f4d8 b355 8786 1723 3041 695d f96a  .....U...#0Ai].j
00000100: f8c0 503b 8df1 eac8 138b 82ed 21cb 9611  ..P;........!...
00000110: 6d6a e5c3 c7ca 637c 26d9 ed7e 107a 14a2  mj....c|&..~.z..
00000120: 6c54 8868 511f 481a 6412 bb95 a771 0401  lT.hQ.H.d....q..
00000130: 3ca4 96cf 7e08 0e31 d967 e4c4 4fee 206b  <...~..1.g..O. k
00000140: 8793 ec23 4da7 44ba 3ded 12e2 b947 9288  ...#M.D.=....G..
00000150: 7809 0ca2 6b04 5f0d e0b2 6717 7e87 0628  x...k._...g.~..(
00000160: 11a3 d282 9d61 f0a4 340c af19 d501 4ddd  .....a..4.....M.
00000170: 1a8c c27b 154c 531f 345c b6a2 7298 a20c  ...{.LS.4\..r...
00000180: e02d bb16 9127 5b42 30d6 634c b7cd 54ae  .-...'[B0.cL..T.
00000190: bb26 9494 2a19 33bc b233 0d8c a75a ccf8  .&..*.3..3...Z..
000001a0: 401c d5f4 bd06 7c43 cd73 32d3 84d0 c440  @.....|C.s2....@
000001b0: 004e b2e9 de84 8251 e080 1a1e f506 e546  .N.....Q.......F
000001c0: cf30 31af 361e b04c 8f5a f636 f1e7 4c24  .01.6..L.Z.6..L$
000001d0: e14b 456b 109e 1421 99e5 ead9 3840 038f  .KEk...!....8@..
000001e0: c1d8 c71a 9b5d 5435 afa0 5eca 34ca a83c  .....]T5..^.4..<
000001f0: 309e 6b5d 532f a0af 20e0 bc3f bb03 a680  0.k]S/.. ..?....
00000200: 6616 4b13 9d09 bf8b 3a93 6f16 b48a e6cf  f.K.....:.o.....
00000210: ccb9 084c 8a35 12a7 447d 8224 4491 e534  ...L.5..D}.$D..4
00000220: 0c71 2f36 fda1 8b54 0808 a144 9894 966f  .q/6...T...D...o
00000230: be74 2140 952c 0294 a1d6 841e 1658 756f  .t!@.,.......Xuo
00000240: 0d7f c5dc 914e 1424 14d9 a5a0 4043 a8c0  .....N.$....@C..
00000250: f434 0200 00                             .4...
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat |file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat |file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

---
## Notas adicionales
Antes de iniciar, entendamos Algunos tipos de compresion en Linux

______________________________________
ext      comp      desc                               ver en consola
_____________________________________________________
.gz       gzip        gzip -d        (gunzip)      zcat 
.bz2     bzip2      bzip2 -d    (bunzip2)      bzcat 
.tar       tar          tar xf                              tar xO
---------------------------------------------------- 
otros (instalar) : 
.zip       zip          unzip (7z x) 
.rar       rar           unrar (7z x)

xxd: Crea un volcado hexadecimal o incluso hacer lo contrario.
## Referencias
https://linuxpasion.com/tutorial-de-comandos-linux-xxd-para-principiantes-con-ejemplos

