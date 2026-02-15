Hello guys !

This level might be somewhat similar to the previous one as we will be using a service which resembles the use of nc 
Openssl is nothing but nc with encryption.
NC deals with tcp but openssl s_client deals with ssl/tls

Just like the previous level we get the password for the current level we are in which is 15
it is located in the /etc/bandit_pass dir.

I got the password and ran the command :
>openssl s_client -connect localhost:30001

and it then opens a blank space where we type in our password of bandit15

That's it !

>bandit15@bandit:~$ la
.bandit14.password  .bash_logout  .bashrc  .profile
>bandit15@bandit:~$ cd /etc/bandit_pass
>bandit15@bandit:/etc/bandit_pass$ ls
bandit0   bandit11  bandit14  bandit17  bandit2   bandit22  bandit25  bandit28  bandit30  bandit33  bandit6  bandit9
bandit1   bandit12  bandit15  bandit18  bandit20  bandit23  bandit26  bandit29  bandit31  bandit4   bandit7
bandit10  bandit13  bandit16  bandit19  bandit21  bandit24  bandit27  bandit3   bandit32  bandit5   bandit8
>bandit15@bandit:/etc/bandit_pass$ cat bandit15
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
>bandit15@bandit:/etc/bandit_pass$ cd
>bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: EC1052DEF59DBE8ED729951466B88796C11D8D67864BFBD69B09307134A178A7
    Session-ID-ctx: 
    Resumption PSK: 4F3D0CB5038FA961145C9EB034F45F0256C5F4C8A3B2E1C3ACB9AAD34B0086FF1F2666E65A6FE8FC7709D0529526C5C6
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 9e e4 b9 b6 dd c1 ab 16-88 78 31 ae 0b 36 ae 89   .........x1..6..
    0010 - 44 63 1f 21 1d 2a d4 64-d2 be 6b 45 67 c5 8f 7a   Dc.!.*.d..kEg..z
    0020 - b7 39 41 ac 49 60 99 61-fd 9f 66 35 0b ae 99 33   .9A.I`.a..f5...3
    0030 - 47 1b c0 d6 4f 11 e0 db-8f 87 f2 74 ba 6d 00 5a   G...O......t.m.Z
    0040 - c6 53 b5 d7 9f 3e 15 d4-43 1f 50 c8 69 b5 20 f0   .S...>..C.P.i. .
    0050 - 51 63 3c c9 80 cc ee 6d-c9 91 7f d0 41 24 7b 03   Qc<....m....A${.
    0060 - bc 8d 2f 25 39 61 75 d8-54 88 9b 22 5c e8 b4 b3   ../%9au.T.."\...
    0070 - d6 95 fc c1 82 79 2a 63-a6 0c 74 93 ce 9a fe cc   .....y*c..t.....
    0080 - 88 60 e6 09 e3 4a 4d 8e-45 05 e3 0f 16 f4 cb 36   .`...JM.E......6
    0090 - 4c 73 c4 38 ee 00 30 35-6f c4 d6 f2 5b 8b 16 69   Ls.8..05o...[..i
    00a0 - 0e 4f 02 d8 f1 52 61 b3-9d f2 fd 79 e0 49 42 68   .O...Ra....y.IBh
    00b0 - 9e 3c e2 65 7d 4f d0 44-ab a9 d6 83 9d ef f9 eb   .<.e}O.D........
    00c0 - d9 b2 dc aa 63 f9 69 cf-93 c5 82 ab 9e 87 22 9a   ....c.i.......".
    00d0 - 3a e6 22 57 38 28 b1 02-c4 94 60 a7 eb 8a 4b 81   :."W8(....`...K.

    Start Time: 1771133547
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: F9A199BF35B8403CDD1A8BF358A48284C5A743BE16DB1513D59D30AA20125633
    Session-ID-ctx: 
    Resumption PSK: DC6882724A6E568ADB8391284B1DAA23B48F4D2BECFDB269AEE77780013DF3B54AC72E0C42D2156788E9469C46D2C7DB
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 9e e4 b9 b6 dd c1 ab 16-88 78 31 ae 0b 36 ae 89   .........x1..6..
    0010 - ec 3f 06 52 bc 99 90 f3-31 73 39 8c 99 e4 31 4b   .?.R....1s9...1K
    0020 - 2a a5 b9 b5 f9 53 86 9e-9f 69 59 fa 89 4c cc 61   *....S...iY..L.a
    0030 - c9 0b 02 51 1d 5c 19 f3-b2 dc ff 00 0a e5 a7 94   ...Q.\..........
    0040 - 8f be 1f 8f 62 96 33 fd-08 f6 8d f7 01 86 80 63   ....b.3........c
    0050 - 55 46 98 42 61 0b de 1c-5e 14 9b 38 af 9b f2 62   UF.Ba...^..8...b
    0060 - 8f 9f 4d e4 e6 36 5c 97-76 95 5c 7c 31 08 b5 e0   ..M..6\.v.\|1...
    0070 - 6d 9c 40 58 0a e1 3b 11-d8 d3 85 69 45 11 d6 d8   m.@X..;....iE...
    0080 - e5 17 02 6a b5 17 8a f7-de 30 ca f8 4c 35 22 fa   ...j.....0..L5".
    0090 - 39 b5 c9 91 67 48 02 66-d0 ee 6b 2e 20 3b ef 41   9...gH.f..k. ;.A
    00a0 - 74 8a 91 43 6e 16 7a 6f-f8 35 fe 44 ae 24 61 26   t..Cn.zo.5.D.$a&
    00b0 - 42 03 43 f7 45 e9 e5 a1-e6 ae e1 55 84 25 ec 57   B.C.E......U.%.W
    00c0 - d1 ea f1 68 f7 f1 18 09-22 d9 d6 c5 da 1c c6 0d   ...h....".......
    00d0 - e2 94 0f 23 3a 21 5f 2e-8e 28 03 9d 82 c4 e8 72   ...#:!_..(.....r

    Start Time: 1771133547
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!                                                                                                                                                    
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx                                                                                                                            

closed

There's the password for the next level that's 16 
Thank you!!

