# WebNet1 

## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Pistas

1.- Try using a tool like Wireshark.

2.- How can you decrypt the TLS stream?

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic/webNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2023-04-01 17:39:33--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                     100%[========================================================>]  90.36K  --.-KB/s    in 0.1s    

2023-04-01 17:39:34 (642 KB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/webNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2023-04-01 17:39:44--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                     100%[========================================================>]   1.66K  --.-KB/s    in 0s      

2023-04-01 17:39:45 (41.3 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/webNet1]
└─$ wireshark capture.pcap                                                                          
 ** (wireshark:61978) 17:42:15.164470 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
 ** (wireshark:61978) 17:43:15.728096 [GUI WARNING] -- FIX Add drag reordering to UAT dialog

^Z
zsh: suspended  wireshark capture.pcap
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/webNet1]
└─$ open vulture.jpg 
                                                                                                                                  
┌──(kali㉿kali)-[~/picoctf/forensic/webNet1]
└─$ strings vulture.jpg -n15
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
```

## Bandera

picoCTF{honey.roasted.peanuts}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
- https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key