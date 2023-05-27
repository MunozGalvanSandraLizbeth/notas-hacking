# shark on wire 1

## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Pistas

1.- Try using a tool like Wireshark

2.- What are streams?

## Solución

```
┌──(kali㉿kali)-[~]
└─$ cd picoctf 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf]
└─$ cd sharkonwire1 
                                                                                                                                  

┌──(kali㉿kali)-[~/picoctf/sharkonwire1]
└─$ 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/sharkonwire1]
└─$ ls
capture.pcap
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/sharkonwire1]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/sharkonwire1]
└─$ cd sharkonwire1  
udp.stream eq 6
picoCTF{StaT31355_636f6e6e}
```

## Bandera

picoCTF{StaT31355_636f6e6e}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap