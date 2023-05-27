# Matryoshka doll

## Descripción

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)

## Pistas

1.- Wait, you can hide files inside files? But how do you find them?

2.- Make sure to submit the flag as picoCTF{XXXXX}

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll]
└─$ wget https://mercury.picoctf.net/static/5ef2e9103d55972d975437f68175b9ab/dolls.jpg
--2023-04-03 17:07:05--  https://mercury.picoctf.net/static/5ef2e9103d55972d975437f68175b9ab/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651634 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                        100%[========================================================>] 636.36K   590KB/s    in 1.1s    

2023-04-03 17:07:12 (590 KB/s) - ‘dolls.jpg’ saved [651634/651634]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll]
└─$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383940, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383940, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll]
└─$ ls
dolls.jpg  _dolls.jpg.extracted
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll]
└─$ cd _dolls.jpg.extracted 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll/_dolls.jpg.extracted]
└─$ ls 
4286C.zip  base_images
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll/_dolls.jpg.extracted]
└─$ open base_images 

┌──(kali㉿kali)-[~/picoctf/forensic/matryhoskaDoll/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ binwalk 2_c.jpg     

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196045, uncompressed size: 201447, name: base_images/3_c.jpg
383807        0x5DB3F         End of Zip archive, footer length: 22
383918        0x5DBAE         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196045, uncompressed size: 201447, name: base_images/3_c.jpg
383807        0x5DB3F         End of Zip archive, footer length: 22
383918        0x5DBAE         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ ls 
2_c.jpg  _2_c.jpg.extracted

┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted  
                                                                                                                                  
┌──(kali㉿kali)-[~/…/matryhoskaDoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd ..                
                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ ls 
2_c.jpg  _2_c.jpg.extracted
                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ cd 2_c.jpg
cd: not a directory: 2_c.jpg
                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg 
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg-0.extracted/base_images]
└─$ binwalk 2_c.jpg     

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196045, uncompressed size: 201447, name: base_images/3_c.jpg
383807        0x5DB3F         End of Zip archive, footer length: 22
383918        0x5DBAE         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg-0.extracted/base_images]
└─$ binwalk -e 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196045, uncompressed size: 201447, name: base_images/3_c.jpg
383807        0x5DB3F         End of Zip archive, footer length: 22
383918        0x5DBAE         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg-0.extracted/base_images]
└─$ ls 
2_c.jpg  _2_c.jpg.extracted
                                                                                                                                  
┌──(kali㉿kali)-[~/…/forensic/matryhoskaDoll/_dolls.jpg-0.extracted/base_images]
└─$ cd _2_c.jpg.extracted/base_images 
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls 
3_c.jpg
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ open 3_c.jpg 
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls 
3_c.jpg
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk 3_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77653, uncompressed size: 79808, name: base_images/4_c.jpg
201425        0x312D1         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77653, uncompressed size: 79808, name: base_images/4_c.jpg
201425        0x312D1         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls 
3_c.jpg  _3_c.jpg.extracted
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_dolls.jpg-0.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted/base_images 
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ open 4_c.jpg 
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                                                  
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 64, uncompressed size: 81, name: flag.txt
79786         0x137AA         End of Zip archive, footer length: 22

                                                                                                                                  
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted            
                                                                                                                                  
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                                                                  
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         
picoCTF{e3f378fe6c1ea7f6bc5ac2c3d6801c1f}  
```

## Bandera

picoCTF{e3f378fe6c1ea7f6bc5ac2c3d6801c1f}

## Notas adicionales



## Referencias
- https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg