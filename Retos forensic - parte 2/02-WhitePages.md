# WhitePages

## Descripción

I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

## Pistas

None

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ wget https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
--2023-03-29 22:04:09--  https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2982 (2.9K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt                   100%[========================================================>]   2.91K  --.-KB/s    in 0s      

2023-03-29 22:04:10 (37.6 MB/s) - ‘whitepages.txt’ saved [2982/2982]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ cat whitepages.txt 
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ ls /la
ls: cannot access '/la': No such file or directory
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ ls -la
total 12
drwxr-xr-x 2 kali kali 4096 Mar 29 22:04 .
drwxr-xr-x 9 kali kali 4096 Mar 29 22:02 ..
-rw-r--r-- 1 kali kali 2982 Oct 26  2020 whitepages.txt
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ wc whitepages.txt                                                                                 
   0    0 2982 whitepages.txt
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ file whitepages.txt 
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1376), with no line terminators
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ xxd whitepages.txt | head
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2 8083 e280 83e2 8083 2020 e280  .  .........  ..
00000070: 8320 20e2 8083 2020 2020 e280 8320 e280  .  ...    ... ..
00000080: 83e2 8083 e280 83e2 8083 2020 e280 8320  ..........  ... 
00000090: e280 8320 e280 8320 e280 83e2 8083 e280  ... ... ........
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ python3 -m pip install pwntools
Defaulting to user installation because normal site-packages is not writeable
Collecting pwntools
  Downloading pwntools-4.9.0-py2.py3-none-any.whl (11.7 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 11.7/11.7 MB 343.8 kB/s eta 0:00:00
Requirement already satisfied: paramiko>=1.15.2 in /usr/lib/python3/dist-packages (from pwntools) (2.12.0)
Requirement already satisfied: mako>=1.0.0 in /usr/lib/python3/dist-packages (from pwntools) (1.2.4.dev0)
Collecting pyelftools>=0.2.4
  Downloading pyelftools-0.29-py2.py3-none-any.whl (174 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 174.3/174.3 kB 225.8 kB/s eta 0:00:00
Collecting capstone>=3.0.5rc2
  Downloading capstone-5.0.0rc2-py3-none-manylinux1_x86_64.manylinux_2_5_x86_64.whl (2.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.8/2.8 MB 298.0 kB/s eta 0:00:00
Collecting ropgadget>=5.3
  Downloading ROPGadget-7.3-py3-none-any.whl (32 kB)
Requirement already satisfied: pyserial>=2.7 in /usr/lib/python3/dist-packages (from pwntools) (3.5)
Requirement already satisfied: requests>=2.0 in /usr/lib/python3/dist-packages (from pwntools) (2.28.1)
Requirement already satisfied: pip>=6.0.8 in /usr/lib/python3/dist-packages (from pwntools) (23.0.1)
Requirement already satisfied: pygments>=2.0 in /usr/lib/python3/dist-packages (from pwntools) (2.14.0)
Requirement already satisfied: pysocks in /usr/lib/python3/dist-packages (from pwntools) (1.7.1)
Requirement already satisfied: python-dateutil in /usr/lib/python3/dist-packages (from pwntools) (2.8.2)
Requirement already satisfied: packaging in /usr/lib/python3/dist-packages (from pwntools) (23.0)
Requirement already satisfied: psutil>=3.3.0 in /usr/lib/python3/dist-packages (from pwntools) (5.9.4)
Collecting intervaltree>=3.0
  Downloading intervaltree-3.1.0.tar.gz (32 kB)
  Preparing metadata (setup.py) ... done
Requirement already satisfied: sortedcontainers in /usr/lib/python3/dist-packages (from pwntools) (2.4.0)
Collecting unicorn>=1.0.2rc1
  Downloading unicorn-2.0.1.post1-py2.py3-none-manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl (16.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 16.1/16.1 MB 495.9 kB/s eta 0:00:00
Requirement already satisfied: six>=1.12.0 in /usr/lib/python3/dist-packages (from pwntools) (1.16.0)
Collecting rpyc
  Downloading rpyc-5.3.1-py3-none-any.whl (74 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 74.0/74.0 kB 682.1 kB/s eta 0:00:00
Collecting colored-traceback
  Downloading colored-traceback-0.3.0.tar.gz (3.8 kB)
  Preparing metadata (setup.py) ... done
Collecting plumbum
  Downloading plumbum-1.8.1-py3-none-any.whl (126 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 126.7/126.7 kB 488.0 kB/s eta 0:00:00
Building wheels for collected packages: intervaltree, colored-traceback
  Building wheel for intervaltree (setup.py) ... done
  Created wheel for intervaltree: filename=intervaltree-3.1.0-py2.py3-none-any.whl size=26098 sha256=c38ffea64145febc3c6a49d9c9c9267eebbc8b797e3a36b970b7bda9cd6735b0
  Stored in directory: /home/kali/.cache/pip/wheels/31/d7/d9/eec6891f78cac19a693bd40ecb8365d2f4613318c145ec9816
  Building wheel for colored-traceback (setup.py) ... done
  Created wheel for colored-traceback: filename=colored_traceback-0.3.0-py3-none-any.whl size=4607 sha256=e1443c1afc033e0182501ed28e0e927997990a7981abf964399e756ebaa79e7d
  Stored in directory: /home/kali/.cache/pip/wheels/45/a9/5f/635d7d8d70eb182fd22f2b0bebce713206e172769bea9f106a
Successfully built intervaltree colored-traceback
Installing collected packages: unicorn, pyelftools, plumbum, intervaltree, colored-traceback, capstone, rpyc, ropgadget, pwntools
  WARNING: The scripts rpyc_classic, rpyc_classic.py, rpyc_registry and rpyc_registry.py are installed in '/home/kali/.local/bin' which is not on PATH.                                                                                                             
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.               
  WARNING: The scripts asm, checksec, common, constgrep, cyclic, debug, disablenx, disasm, elfdiff, elfpatch, errno, hex, libcdb, main, phd, pwn, pwnstrip, scramble, shellcraft, template, unhex, update and version are installed in '/home/kali/.local/bin' which is not on PATH.                                                                                                                  
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.               
Successfully installed capstone-5.0.0rc2 colored-traceback-0.3.0 intervaltree-3.1.0 plumbum-1.8.1 pwntools-4.9.0 pyelftools-0.29 ropgadget-7.3 rpyc-5.3.1 unicorn-2.0.1.post1

from pwn import *

file = open ('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)
print(data)

┌──(kali㉿kali)-[~/picoctf/forensic/whitepages]
└─$ python3 exp.py.save
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}\n\t\t'
```

## Bandera

picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt