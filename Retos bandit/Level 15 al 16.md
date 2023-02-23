# Bandit Level 15 → Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso al nivel
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
## Solucion

```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 06:20:29 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 06:20:29 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 06:19:29 2023 GMT; NotAfter: Feb 21 06:20:29 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEA7qUdzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMDYxOTI5WhcNMjMwMjIxMDYyMDI5WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDL
vM0gZzAHdXTeD5t4ruUJo/kRs4UAodA9XcqDhNtW464W0c55RqKLp921syy3Lvjr
8Q9WkqvCFX+efShMd8XnzbT/dyRrD+cZQnSiPJ3bwDdpwqfkl9h3mb609Kb5HI6R
JgogEyuRLJI+HKtr/wXHwo1vBZ0+yaPMX6sdkd6Hu5Ra0L5Q5+E5+3F/8QgvCeVE
hDRIOrh2a7jxykb8G6+xVC6jIZY0YfrZz6LrESyQau256pqyaQPqQoUWTlitxIql
Ym2Baw7vYDxmFZrvj0FkumC6NokX6K2G9bZ0DaKR/DspPdAC4oT81SawJvsBibdN
51VI6dxBn412ZS8bS155AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQA9
skxWNwZbedjaVTa5yMPUZQ4Nf5/LAAMtS5Q7mzGH5tdQsTGR0Z4n4eA4hzrmzHBF
MVRL5mR9n+sM5pIrKDa6f4zIc5ObxDyN19ie+3SFASCPz9tihK8Js2V8qsR6LHV1
pfD8DSG0hZPtUuK3Mfi+nWqQUFiiTGj30mb9vlS1sSWv5PGznou1gQ3ZfrDs7B4K
ZKZrllPIVV1CrlDw2Bv8Dc432LQuZAmKAjBd6FG0OAboU/WJMTwAfVjlKMtvC8tg
DZ3djSTprq6PrXlI0utw/MsMIh69b61BRXUuDvRxhU11SNmSI8aegjVL8KuK+Euh
sSLPTocV29SY1YXOwEQi
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
    Session-ID: A32935D5F219830F5A9D440B83186832B7B73C1AE284D542DB6F9B8DB9729ECE
    Session-ID-ctx:
    Resumption PSK: 30DF7FB4816418FCC68C9E705179FC287C6465060AF905C5648839C8C6371CC08E9DDB4397ECAFF99114E5FA1F6ABE0C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ee ae 09 e4 56 06 6c 9e-c9 80 86 77 50 83 15 59   ....V.l....wP..Y
    0010 - 42 f1 28 2c 64 f6 28 74-53 56 b2 d6 ce f9 d1 0f   B.(,d.(tSV......
    0020 - e4 af f6 2b 90 cb 5f 74-3d 44 5b 18 12 e7 59 66   ...+.._t=D[...Yf
    0030 - db 02 62 69 3c 7e d5 c8-73 93 5f 96 fd f0 f2 d0   ..bi<~..s._.....
    0040 - 3e 2f 17 7e 0a b3 74 e2-c7 9a a3 a6 03 bf 53 26   >/.~..t.......S&
    0050 - 06 27 c3 f4 fc 4a 14 e6-72 0e 50 4c f2 75 d4 11   .'...J..r.PL.u..
    0060 - 48 e3 94 2d 36 aa f3 43-52 6c d6 bc ab f9 bb 1c   H..-6..CRl......
    0070 - 3b 52 8d 16 6d d1 72 17-5f f2 cc ce da fd 8c a7   ;R..m.r._.......
    0080 - 3b 9a 78 c1 17 e1 cd c5-c5 c1 04 cb b3 70 95 a3   ;.x..........p..
    0090 - 83 bd 1a e1 f0 6e d1 3c-fd 34 d9 0c 2f f9 75 1e   .....n.<.4../.u.
    00a0 - 4b 32 57 06 7b 90 51 64-89 3a a8 3a 75 52 bc e5   K2W.{.Qd.:.:uR..
    00b0 - c1 62 4f 6e 67 c5 a1 4c-6d e1 d8 dc 17 96 c2 34   .bOng..Lm......4
    00c0 - 99 8e d2 d2 44 93 62 02-78 30 57 94 8e d7 57 9e   ....D.b.x0W...W.

    Start Time: 1677007528
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
    Session-ID: A6712BAA112D13A3A53E22030693FA96560C7F5CDC552308E03B69075D99A8F1
    Session-ID-ctx:
    Resumption PSK: 92FA57049B6490BE0C9D36B668BF2E2A34261E17757B5F06A538AE2E0893833E664FCE3BCCC9C87AB0A59F5448E25EAD
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ee ae 09 e4 56 06 6c 9e-c9 80 86 77 50 83 15 59   ....V.l....wP..Y
    0010 - 4d f6 ac c2 be 8d 3c 60-4f e6 9a 07 c4 a5 18 29   M.....<`O......)
    0020 - 3b 59 ab 16 b5 da 07 46-7c ac 46 d5 0c b0 12 3b   ;Y.....F|.F....;
    0030 - 9b 68 12 d1 cb 0c ab 5b-97 4e 8d 7c 15 15 a9 40   .h.....[.N.|...@
    0040 - 65 7e 0e 3b d7 62 7f 89-fd de 9b d4 16 75 e7 a8   e~.;.b.......u..
    0050 - 9a 69 28 e7 5d f1 2d e0-d6 72 15 46 df a2 e6 24   .i(.].-..r.F...$
    0060 - 3f a3 7e 0f ce a4 e7 f0-be ad 11 35 70 44 d0 e2   ?.~........5pD..
    0070 - 81 2b 9c d6 a1 3a 4a 6a-3e 24 78 51 38 1f b8 16   .+...:Jj>$xQ8...
    0080 - 0d 96 cd fe e3 12 36 7f-95 37 b4 1f d1 6f 2c 78   ......6..7...o,x
    0090 - 5f d9 76 9d 97 fe 57 d0-b1 66 24 c7 91 62 fe 1d   _.v...W..f$..b..
    00a0 - 94 c3 25 89 69 f0 1d d1-9c 6a b5 d8 41 7f a7 94   ..%.i....j..A...
    00b0 - db 9b 92 12 a6 d9 df b2-bf 8e 61 4c 42 6d df 7f   ..........aLBm..
    00c0 - 97 60 16 57 ec 7d b2 20-f1 f7 34 ae c8 20 cf 27   .`.W.}. ..4.. .'

    Start Time: 1677007528
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
```

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias