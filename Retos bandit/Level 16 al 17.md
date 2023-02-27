# Bandit Level 16 → Level 17

## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso al nivel
ssh bandit16@bandit.labs.overthewire.org -p 2220
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solucion

```bash
bandit16@bandit:~$ nmap -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-27 22:49 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00014s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 24 22:59:05 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 24 22:59:05 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 24 22:58:05 2023 GMT; NotAfter: Feb 24 22:59:05 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEXaCVVzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjI0MjI1ODA1WhcNMjMwMjI0MjI1OTA1WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDP
cZ+PR+x7nAI6TVhZvc6x5//nXHJUZnIv2kf6x8SOY5al5BV8I5njUSVQef9fQNE2
JlBdoYNJ65jgzYWrVqPCObCqrPsHZHf8pMD/iElYUcD5u/qtNReuVPfeYefxCvBg
Cy0MltMiLGskDn3rDSwCRWNB2jr9+jQYa7rIGDyWCAq4WH/IsWtF6tan25Bqe6tp
LIMJhuAH56EjZ0biNJ3aOgsWHwqS1bBdMzURABvR+PZc0mikWaNjb2R0d8v0gJTf
qz0qkea6IstFSfwEu2FdslmDZ8PWlIwexw3erL+Ae0L2mFhdf3g1nkUARl8R0Bbe
L9/rtYsV7dF3KG7CFJbbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBH
HpXhIirw6+X3VNmrtXw7HjpriGDA1UTjP2yfeu2YuLIm83iUpz3HuiiwsfJJX9HY
VeDQnJjgMekib2qbq99OHkz+4jFKpw0zR7wTa9K8fifkrQHW/KJOVg1fmJCyFl+j
LF06QYp5f8yA+I2ICGKuNSXd3NvYEVh0tWVXemx/oXqQLHUFBjWNcyBDfCnfZIfe
jhHPhGj/9DuJJWx1lBEOIFHrfOj2uge0R5YZvU0kEm3IQ6iabWM2JF8MHOWWYX8s
wXL4aeNo+K4lnz3wjqnRfSClTwTo9zvaaq+Ym8UxPx3w7SmAU3CXbLh/ukYR6xYp
YEsSAXuYvKkxrTvey2Ik
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
    Session-ID: 4046150AFAFF14A2B97745A01924A5C063C772DCC3A9CD35676EFE32BCD96928
    Session-ID-ctx:
    Resumption PSK: D1E87CA77DB92449F2E2B3F1F73FF5791052ABA42D73035F39CA3DA970A58736AA02F5F53D5E4441A5F32B9E82E86DA3
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 70 f2 f5 0a f4 da 59 2b-66 40 bc 3c 8d 67 67 76   p.....Y+f@.<.ggv
    0010 - e5 22 61 3e f6 27 bc a3-63 e2 03 2b 41 f1 ac b0   ."a>.'..c..+A...
    0020 - 6f 4d f5 85 7a 1c 4a b3-f9 55 f2 c9 ae a2 c8 df   oM..z.J..U......
    0030 - 72 4a 1d 33 2b 9e c8 db-55 dd b3 8e 7f 03 fe 13   rJ.3+...U.......
    0040 - 6f c8 0e 33 16 03 71 3c-e7 b0 c0 98 cb 9f 38 48   o..3..q<......8H
    0050 - 29 1b 35 78 63 83 d4 74-76 98 f1 6d fb 28 9c 59   ).5xc..tv..m.(.Y
    0060 - 8f 42 77 92 dc 8f 47 c7-dc 37 ed e3 1d 0c 8c a6   .Bw...G..7......
    0070 - d7 ef 88 48 68 e1 41 50-31 3b 62 ed 20 f6 6b 8a   ...Hh.AP1;b. .k.
    0080 - 1d 7d f3 72 d6 e5 55 ce-26 f9 79 83 4c 04 e1 4b   .}.r..U.&.y.L..K
    0090 - 9f 05 22 26 b6 e6 85 8f-ff c7 69 8e 03 06 da 56   .."&......i....V
    00a0 - f7 e1 f5 1a 5a 04 1c 38-7d 8e 74 aa db 35 8b 21   ....Z..8}.t..5.!
    00b0 - ef 6f f2 97 4c a9 73 94-87 fd 64 b5 e2 a3 10 e1   .o..L.s...d.....
    00c0 - 23 f1 16 42 30 81 27 85-25 e4 7a de 51 81 1d 87   #..B0.'.%.z.Q...

    Start Time: 1677538203
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
    Session-ID: 6D0869AACBB6248DD1D841EAFFB4C6AFBE59F3A839D688CA6054513AFA5644B4
    Session-ID-ctx:
    Resumption PSK: 3308AF346A8EB793B3546E5807F2E39C66C3856C01F2E7E6A29A6C33254272A5AC6C0CB598DAF99EE559DA7C724D8A91
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 70 f2 f5 0a f4 da 59 2b-66 40 bc 3c 8d 67 67 76   p.....Y+f@.<.ggv
    0010 - 67 45 65 45 72 87 e8 f6-0b cb 00 b9 3b 2f 17 b7   gEeEr.......;/..
    0020 - dc ec 4e f6 f3 e1 3f 76-1a d0 81 7f f3 db 19 e2   ..N...?v........
    0030 - f4 7b de f7 cc 01 97 b7-b2 28 97 4e bc 90 f1 26   .{.......(.N...&
    0040 - 3d 7e 7f 98 b2 d9 b4 e1-8f da 24 de d3 d7 d2 d2   =~........$.....
    0050 - e8 64 f2 d6 99 6f f3 1b-ef fc f6 b3 46 74 1f b8   .d...o......Ft..
    0060 - 5b 95 7a e5 eb 8b 49 2c-cc ef eb fd b5 dc bd c3   [.z...I,........
    0070 - 87 3c f9 d3 d5 5e fb 3a-ea fb f8 a2 75 04 15 24   .<...^.:....u..$
    0080 - af 52 4e 2c d0 e3 1c 0b-98 9a ae bc fb 69 6c 6c   .RN,.........ill
    0090 - fe d8 39 16 d9 e6 0f db-49 dc aa 39 19 51 90 cd   ..9.....I..9.Q..
    00a0 - 68 47 46 39 cb 67 cc 4f-b5 4e 22 b7 bb c2 cf fe   hGF9.g.O.N".....
    00b0 - 8f 18 a2 47 06 76 a6 67-59 57 85 69 ba f7 4e 94   ...G.v.gYW.i..N.
    00c0 - 0e c9 bf 2e 61 a9 2f 5b-40 84 6f 2c a1 b7 df c9   ....a./[@.o,....

    Start Time: 1677538203
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$
```

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias