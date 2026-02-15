Hello guys! 

Level 16 might be a kinda same to the previous one though here we will be using openssl s_client rather than netcat 'nc' 
So firstly as I get into the ssh

I first did a port scan on the local host with the following command .

>bandit16@bandit:~$ nmap -p 31000-32000 -sT -sC localhost

Starting Nmap 7.94SVN ( https://nmap.org ) at 2026-02-15 11:02 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00016s latency).
Not shown: 996 closed tcp ports (conn-refused)
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
| ssl-cert: Subject: commonName=SnakeOil
| Not valid before: 2024-06-10T03:59:50
|_Not valid after:  2034-06-08T03:59:50
|_ssl-date: TLS randomness does not represent time
31691/tcp open  unknown
31790/tcp open  unknown
| ssl-cert: Subject: commonName=SnakeOil
| Not valid before: 2024-06-10T03:59:50
|_Not valid after:  2034-06-08T03:59:50
|_ssl-date: TLS randomness does not represent time
31960/tcp open  unknown





done: 1 IP address (1 host up) scanned in 1.74 seconds

As we can see 31518 and 31790 ports are the only ports which wre running ssl on them.

lets try connecting both of them first with 31790

>bandit16@bandit:~$ openssl s_client -connect localhost:31790
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
    Session-ID: 16C8D2F911D12D622066E3F565F7E02451063C9220F8B59A3904A4E175E5D28A
    Session-ID-ctx: 
    Resumption PSK: 007E73373B53A559176C3C0E76676E173230C0CB31A211EC796BC79C7057DBD76974E055BA0B59CD0BA7E554E0EB22C4
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 87 59 c3 07 f5 a3 44 6a-d7 8b ef 81 ba 7d 4d 54   .Y....Dj.....}MT
    0010 - fb cf bb 66 32 1d b4 af-bb 6c c4 e9 fa 0e e2 9f   ...f2....l......
    0020 - 8d 42 03 3a a5 61 02 ab-49 01 c6 8f 15 10 22 e2   .B.:.a..I.....".
    0030 - 19 c9 eb 02 07 d2 81 5b-64 7d d8 b8 da f3 9e ce   .......[d}......
    0040 - 82 b6 91 1d ea 9f b9 b1-bc bc c1 e0 06 e5 c5 42   ...............B
    0050 - 05 4f dc 0a d5 f9 29 28-a3 22 ba ca d2 d6 49 23   .O....)(."....I#
    0060 - 92 05 e4 bf b1 37 cc 5e-58 eb 4d e0 2c d0 d3 d4   .....7.^X.M.,...
    0070 - 36 2d 61 fe 4f d9 0a 2a-9c 1a 03 69 05 53 ae 15   6-a.O..*...i.S..
    0080 - e8 95 d4 e5 03 a4 e1 2a-f1 1d 95 c9 6f 16 7e de   .......*....o.~.
    0090 - e5 81 5d 29 2f d2 52 f8-ca 0e 57 3a 2c 86 51 bc   ..])/.R...W:,.Q.
    00a0 - 7b f0 15 50 f0 7b 2c 4c-9a 52 0c bd 1b 45 5b 80   {..P.{,L.R...E[.
    00b0 - e1 10 0d 1f 8a da d5 cd-60 bd 8e 9e dc 8e 56 10   ........`.....V.
    00c0 - 4e 47 5d 1c cd 32 fd 7a-11 d3 83 1d ca 65 e5 38   NG]..2.z.....e.8
    00d0 - 9a 2f 23 a7 8d df 6e 0d-32 c8 59 ee 2d db 7c 2d   ./#...n.2.Y.-.|-

    Start Time: 1771153886
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
    Session-ID: 25B5F9451ECC5C59F4E9D43721177B36876154040D24C8F5F2172C664DB9310D
    Session-ID-ctx: 
    Resumption PSK: 85193C7CDA167C6C175108E5A6833E7324A807DE1A60FB5916BE062B6AA77BBB894EA86B8AD046386C76C49016BB9034
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 87 59 c3 07 f5 a3 44 6a-d7 8b ef 81 ba 7d 4d 54   .Y....Dj.....}MT
    0010 - a9 10 ab 8d 46 64 c5 e0-87 b3 26 6b 91 35 58 98   ....Fd....&k.5X.
    0020 - 83 67 0d bf e5 c7 04 de-7a a0 aa 2c 07 b7 ce 00   .g......z..,....
    0030 - 32 bf 80 29 7e 07 64 4c-e5 53 27 44 37 cf 2a 73   2..)~.dL.S'D7.*s
    0040 - e6 3d 21 73 79 09 c5 23-ef c5 36 23 ef 09 20 ed   .=!sy..#..6#.. .
    0050 - 3b 53 5c 36 de c0 5e 58-87 e3 b6 8c 59 0d df c7   ;S\6..^X....Y...
    0060 - b3 4a c6 9e f7 54 d5 85-71 30 2d 13 e9 05 3a e7   .J...T..q0-...:.
    0070 - ec 65 a5 5e df f6 5d cb-43 31 75 1f c6 64 94 e7   .e.^..].C1u..d..
    0080 - ef bd 9e 8c 8a 66 c5 b3-cb 93 1c bb d2 e9 05 74   .....f.........t
    0090 - 4f 62 e1 88 e3 7a 1f 8e-ab e6 50 a5 f0 63 15 f7   Ob...z....P..c..
    00a0 - cd 14 53 1b f8 a3 be 43-0b 55 16 f6 34 78 fd 5a   ..S....C.U..4x.Z
    00b0 - 57 e8 2d 00 84 d4 4a 47-c4 49 82 59 10 75 c0 db   W.-...JG.I.Y.u..
    00c0 - cf c9 52 1d 5e 72 8a a0-36 5e 5c 95 5e 85 42 13   ..R.^r..6^\.^.B.
    00d0 - 58 9c 83 94 e3 c1 02 cb-8a 47 52 41 85 12 e0 39   X........GRA...9

    Start Time: 1771153886
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK

So we take that private key in a file called sshkey17.private


_____________________________

ignore that above part

bandit16@bandit:~$ openssl s_client -connect localhost:31790 -quiet
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
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

Thats it we save it and use it 
thank you 
