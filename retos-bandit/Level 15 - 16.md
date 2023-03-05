# Level 15 - 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso al nivel
Contraseña para el nivel 15: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
---
bandit15@bandit:~$ ls
bandit15@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Feb 21 22:02 .
drwxr-xr-x 70 root     root     4096 Feb 21 22:04 ..
-rw-r-----  1 bandit15 bandit15   33 Feb 21 22:02 .bandit14.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Mar  4 13:56:53 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Mar  4 13:56:53 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Mar  4 13:55:53 2023 GMT; NotAfter: Mar  4 13:56:53 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIER13gCDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMzA0MTM1NTUzWhcNMjMwMzA0MTM1NjUzWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCM
/lC68OElsJpJiTKTUulHdeAi5bOTxIvyJY2MIl18kTWHsbpiHv98GnAaSvcOQ9Ks
o+wSOho73O2iGtlHWvXyeXYH4AixWPpV8zYkV74mfXKpPVd5x4mIcCYLRwos2Zuk
TZh/s0TuvZBb/SUhwk2l0O6I3ZxR1j51sHq0oOu05kIK7C15KmTFLJNTk9x/49HX
oTMW6LvmD3P3itrcfXawsdqth9TXIm1+G9pGYRgH7MHoUSfWxYxViR7D2Vl4p83j
XjNmFd64xGWIHWqd6g6EXetgUCxrwJZLnEh6gdCXAMI+oc5VppbZqNY7F3RBGe+E
65JVfnnDyMf6gj3UPF/xAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAt
25iuaIxZQ8aEfCCLYBk3EqM+5HBvOTvGLd/8z0ccYs6DTs/WPHaRQBVzo8AlQSnG
tL2mSrfhM3VjwVLdDmC1BzYDMduSnI8EAriOmrxmb3Bm7zbyvRxS6kOqoYoeMeCm
sRC7SQ/r/yFlEGjLyq2uYlegz0wz2OJZVRLUGZtD43hwJXZ8+22BVC5sAOrayI0e
0kY6ZHK59TUYByzWLMQyZD7vFaPcyHXfTgRMTPHrZrVFzmmoj9j62+wee1L18PII
JXIkypLxF/k3Eqne+OuQXFXIrw+OF6/RZJ8St9NYGM40ItzqOYvcNZISPFEt7aVI
9VaN/wiSFPbWU1o+8mG5
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 044BC9C9AAB75396D56EBA320C3C79A768D78F302ABD5DC00DF6709301C98A72
    Session-ID-ctx:
    Resumption PSK: BE35E317C9870DBA342BDC4B667AFE25910CAFF22EF47148A181C4007F29EEC56027C93247EE2C0E146216D2636701EB
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 29 74 c5 c9 dc 35 ec 9a-f5 71 ec 0b 1e 96 90 49   )t...5...q.....I
    0010 - 7a d6 a3 7c e8 89 42 ee-f0 5b 69 d5 6d 99 88 17   z..|..B..[i.m...
    0020 - 54 3c 58 0f 3a 58 58 45-32 67 7c 34 8c ea e8 9f   T<X.:XXE2g|4....
    0030 - b1 4d 6a 4e c3 4f a3 3e-84 e5 89 51 76 55 b0 dc   .MjN.O.>...QvU..
    0040 - 99 89 8f 7c 15 03 e3 ad-d5 14 49 b6 d9 14 96 3a   ...|......I....:
    0050 - be 63 d8 a6 37 ae bd f6-52 a2 6f d4 4d e7 38 05   .c..7...R.o.M.8.
    0060 - c4 19 4c ad 50 25 62 78-3d 33 a8 2b 69 77 f3 98   ..L.P%bx=3.+iw..
    0070 - cf be bb 33 0f 24 e5 44-86 72 fe 52 15 9d b1 b7   ...3.$.D.r.R....
    0080 - 25 92 ce ca 34 3c a5 dd-ac 84 49 94 37 10 38 49   %...4<....I.7.8I
    0090 - 7a bf 25 ce 19 ce a8 01-12 64 fb d2 59 42 06 88   z.%......d..YB..
    00a0 - 95 84 39 0a 4e cb f9 fe-7a 54 c9 8e 26 60 c9 d2   ..9.N...zT..&`..
    00b0 - 95 fe 6a d7 b9 90 3b be-c4 1e 0b d1 5a 75 aa fa   ..j...;.....Zu..
    00c0 - 4c 80 31 f3 54 7b b3 65-6d fd 46 e7 b5 2a ec a2   L.1.T{.em.F..*..

    Start Time: 1678041485
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 84D1CBA8198A325B325920E9E183CD752662CA82C63ED3E1E63B0BAC0CBE8E14
    Session-ID-ctx:
    Resumption PSK: A8EB4A3C021C93010AC00A644013686E751F05D79217B9A16F539AC101462F546E8F86A34B6B1F86BBAE035A60C2CA9C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 29 74 c5 c9 dc 35 ec 9a-f5 71 ec 0b 1e 96 90 49   )t...5...q.....I
    0010 - d3 fe 8e 6c 4d 97 71 42-09 8d dc 59 cc 0b 8c 56   ...lM.qB...Y...V
    0020 - 8c 8a a3 ab 38 59 da ae-2c bc 9c a7 3f 0e 4d 8d   ....8Y..,...?.M.
    0030 - 50 84 e3 b5 ef 0f 20 2b-a6 e0 dd 88 f0 e7 1b bf   P..... +........
    0040 - 49 48 b7 74 e4 02 e4 df-89 33 2f 1c 8b be 53 6a   IH.t.....3/...Sj
    0050 - 2f 3c a9 7e 56 23 4d df-01 22 93 80 72 52 41 69   /<.~V#M.."..rRAi
    0060 - 8b 6d f6 63 01 e0 3f 09-fd 21 5d 8e ac b7 f4 72   .m.c..?..!]....r
    0070 - 63 04 c1 d7 78 38 6f e8-bb 41 10 cc dd 10 24 81   c...x8o..A....$.
    0080 - fb d7 2c 35 35 73 55 6c-04 30 32 70 f3 f9 4f e9   ..,55sUl.02p..O.
    0090 - 9f 74 12 aa cd bc 77 72-96 e7 6f f7 c6 d5 b8 ae   .t....wr..o.....
    00a0 - f2 f7 b4 b8 ba 26 32 68-8d 6c db b0 64 7b 8c 4d   .....&2h.l..d{.M
    00b0 - cf 41 73 59 1d a4 db a2-7c 1d bb c8 20 06 6e 12   .AsY....|... .n.
    00c0 - 6d 0e 68 4b ab d7 55 98-70 2b 85 dc 02 ba a8 09   m.hK..U.p+......

    Start Time: 1678041485
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$

---
## Notas adicionales
openssl: Realiza la verificación desde Linux

## Referencias
www.sysadmit.com/2018/10/linux-verificar-caducidad-certificados.html

