# Trabalho realizado na Semana #11  - Public-Key Infrastructure (PKI)

## Setup


![Setup](setup.png)

## Tarefa 1

```sql
[01/21/22]seed@VM:~/.../PKI$ cat ca.crt 
-----BEGIN CERTIFICATE-----
MIIDlzCCAn+gAwIBAgIUVlut6QZiNtwriQb2iUlSn3G7OhswDQYJKoZIhvcNAQEL
BQAwWzELMAkGA1UEBhMCUFQxDjAMBgNVBAgMBVBvcnRvMQ4wDAYDVQQHDAVQb3J0
bzENMAsGA1UECgwERkVVUDEMMAoGA1UECwwDRlNJMQ8wDQYDVQQDDAZMMDNHMDcw
HhcNMjIwMTIxMTYzNTU0WhcNMjIwMjIwMTYzNTU0WjBbMQswCQYDVQQGEwJQVDEO
MAwGA1UECAwFUG9ydG8xDjAMBgNVBAcMBVBvcnRvMQ0wCwYDVQQKDARGRVVQMQww
CgYDVQQLDANGU0kxDzANBgNVBAMMBkwwM0cwNzCCASIwDQYJKoZIhvcNAQEBBQAD
ggEPADCCAQoCggEBAMzRY75n52W6Ww0mbbI5BVOoqxbfMICSoLt51gy+rqAaXvD4
518wszC3U0UhdjaRZh3FAUnT2WNL05DyDswYdHl5mtSVOpji9dochOq/xYtMf2Fn
7nwQwWWB5PQieWYFvcITNv4HGEYOPskwahaQ3OhPqp27ExmRNdckN0MHizXZR0c6
pPMiArT4x9kwghdHJ03HSP8RF2JAf5XncNY8j9T0avdfbChqBvALQBi/Te2CJB+H
AOE6I7a4RKCME7+DWwFEGZ5uRO8lweO2Ul3yjofs8GWh7v+LSNmzDYX1hhr6DFxd
1hJDZ7H4JHfaFwgrh4cTgy++/NVIR5qlHSGQFt8CAwEAAaNTMFEwHQYDVR0OBBYE
FH3Dxuqx5VrISL9mtg+nxtr7dbUkMB8GA1UdIwQYMBaAFH3Dxuqx5VrISL9mtg+n
xtr7dbUkMA8GA1UdEwEB/wQFMAMBAf8wDQYJKoZIhvcNAQELBQADggEBAIRGAxGf
cR/scvhexQbGmV8DdiRU/tO9jzX/ZSNdZSMyhIezlDWRCSHKS7z2JDC2x3EKedj0
CY2GgADKXqP+EXKbDT91YB8XWhwZ0LQgvt/DqsMY4VFpPSHgKDDSw86br+MlCJO3
SNmJSdprPy1i7HURcLm52LBOZO792fP00TJWEm6/gytTPFEQq158S68JpT27ePOx
kUalVnXSJtXtcHxlXecV0Yhg7AbtgKjAJdywMFPFTBAjTk4yy3qALUsaUNHya9tk
ENr+Y+k53vjoz0Kgs9N+fI2TNgXlmq59veu43SqAz238PwzV+5g50hKKn6nMs+i/
rKSahwbnnEXGRLE=
-----END CERTIFICATE-----
```

```
[01/21/22]seed@VM:~/.../PKI$ openssl x509 -in ca.crt -text -noout
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number:
            56:5b:ad:e9:06:62:36:dc:2b:89:06:f6:89:49:52:9f:71:bb:3a:1b
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: C = PT, ST = Porto, L = Porto, O = FEUP, OU = FSI, CN = L03G07
        Validity
            Not Before: Jan 21 16:35:54 2022 GMT
            Not After : Feb 20 16:35:54 2022 GMT
        Subject: C = PT, ST = Porto, L = Porto, O = FEUP, OU = FSI, CN = L03G07
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                RSA Public-Key: (2048 bit)
                Modulus:
                    00:cc:d1:63:be:67:e7:65:ba:5b:0d:26:6d:b2:39:
                    05:53:a8:ab:16:df:30:80:92:a0:bb:79:d6:0c:be:
                    ae:a0:1a:5e:f0:f8:e7:5f:30:b3:30:b7:53:45:21:
                    76:36:91:66:1d:c5:01:49:d3:d9:63:4b:d3:90:f2:
                    0e:cc:18:74:79:79:9a:d4:95:3a:98:e2:f5:da:1c:
                    84:ea:bf:c5:8b:4c:7f:61:67:ee:7c:10:c1:65:81:
                    e4:f4:22:79:66:05:bd:c2:13:36:fe:07:18:46:0e:
                    3e:c9:30:6a:16:90:dc:e8:4f:aa:9d:bb:13:19:91:
                    35:d7:24:37:43:07:8b:35:d9:47:47:3a:a4:f3:22:
                    02:b4:f8:c7:d9:30:82:17:47:27:4d:c7:48:ff:11:
                    17:62:40:7f:95:e7:70:d6:3c:8f:d4:f4:6a:f7:5f:
                    6c:28:6a:06:f0:0b:40:18:bf:4d:ed:82:24:1f:87:
                    00:e1:3a:23:b6:b8:44:a0:8c:13:bf:83:5b:01:44:
                    19:9e:6e:44:ef:25:c1:e3:b6:52:5d:f2:8e:87:ec:
                    f0:65:a1:ee:ff:8b:48:d9:b3:0d:85:f5:86:1a:fa:
                    0c:5c:5d:d6:12:43:67:b1:f8:24:77:da:17:08:2b:
                    87:87:13:83:2f:be:fc:d5:48:47:9a:a5:1d:21:90:
                    16:df
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Subject Key Identifier: 
                7D:C3:C6:EA:B1:E5:5A:C8:48:BF:66:B6:0F:A7:C6:DA:FB:75:B5:24
            X509v3 Authority Key Identifier: 
                keyid:7D:C3:C6:EA:B1:E5:5A:C8:48:BF:66:B6:0F:A7:C6:DA:FB:75:B5:24

            X509v3 Basic Constraints: critical
                CA:TRUE
    Signature Algorithm: sha256WithRSAEncryption
         84:46:03:11:9f:71:1f:ec:72:f8:5e:c5:06:c6:99:5f:03:76:
         24:54:fe:d3:bd:8f:35:ff:65:23:5d:65:23:32:84:87:b3:94:
         35:91:09:21:ca:4b:bc:f6:24:30:b6:c7:71:0a:79:d8:f4:09:
         8d:86:80:00:ca:5e:a3:fe:11:72:9b:0d:3f:75:60:1f:17:5a:
         1c:19:d0:b4:20:be:df:c3:aa:c3:18:e1:51:69:3d:21:e0:28:
         30:d2:c3:ce:9b:af:e3:25:08:93:b7:48:d9:89:49:da:6b:3f:
         2d:62:ec:75:11:70:b9:b9:d8:b0:4e:64:ee:fd:d9:f3:f4:d1:
         32:56:12:6e:bf:83:2b:53:3c:51:10:ab:5e:7c:4b:af:09:a5:
         3d:bb:78:f3:b1:91:46:a5:56:75:d2:26:d5:ed:70:7c:65:5d:
         e7:15:d1:88:60:ec:06:ed:80:a8:c0:25:dc:b0:30:53:c5:4c:
         10:23:4e:4e:32:cb:7a:80:2d:4b:1a:50:d1:f2:6b:db:64:10:
         da:fe:63:e9:39:de:f8:e8:cf:42:a0:b3:d3:7e:7c:8d:93:36:
         05:e5:9a:ae:7d:bd:eb:b8:dd:2a:80:cf:6d:fc:3f:0c:d5:fb:
         98:39:d2:12:8a:9f:a9:cc:b3:e8:bf:ac:a4:9a:87:06:e7:9c:
         45:c6:44:b1

```

---


```sql
[01/21/22]seed@VM:~/.../PKI$ cat ca.key
-----BEGIN ENCRYPTED PRIVATE KEY-----
MIIFHDBOBgkqhkiG9w0BBQ0wQTApBgkqhkiG9w0BBQwwHAQIgCOPNyQE51ICAggA
MAwGCCqGSIb3DQIJBQAwFAYIKoZIhvcNAwcECF46Bo+K5TN+BIIEyF9Tp/r4GecE
2lPdMQQ10riEpC1v0E5f26fC6lwaYY2SsCBb9mubwSN1lTOGDp+LjWAfNbMlR8oB
Jlt8NUoOvJKHMXhVzyu3dH7qZPOPkZvpqrpRjzdpb+cOaOCiOmgHx3DWQUBZpqHt
ncCqD2mdG+M5yPOLozQi4vKMPI+BW8LLNRr1TQ9Mk7m7o/M1/lDpPkccUQ/GE9hs
O5TYJYdzYdT5395vBPAqxdHIlEkA956xMEaJe3Hj2pdxHRzhw8v8rGvLIpdji2V8
6p6RcsIMSgyn/ixx64OtC31TfMJSCc8QR0Id2Y/B4p8omkk4SuuaJ5MAtzux2Xjo
+x3VfbdNS8X4ZnaWdGlxkVeGU9HUCzS02imEVzgbiJ/DZWFbT/wHtos4cA7FZOGw
9Rp8GOUTFtyvFbjENGZqxNuKhbdcVj+CRmPkGIJoI9cSmMI6QzzvTB3SdtI3bI+h
BZGjjwyJxs0vVLhrFZ/lxZH9VCw1gcr2gUULcbYylPf4zSAjC9hDE2bEqe9Wfux1
DXl/QE94mv3INqyUMGz8FCU8R9g/UgZEd/ov6SfGqavyIwwrkQNwjeV2pANa7uZm
WZxABGKGLveGmtVN5aypeXmq2aq9FJ/tjV9oRfiZla8WzBXJcMD/VqYIXYY41eFV
3NZHcMq8uj71I/GzLXxEQy9BvKkaEKOk80EZP03JKfVb6VhVPDy56nB7CrUF7wef
WHUY68wkqQCWGCLs7xho8xYIWzN6scjNSw/Sae7i7wZcjYmlqy4L8dpKCRadB56v
3zz1eofZ7FnAsdAYnYlTyWfNgTxWHX8PRMXKrfmY9enufGNpnAjL9MgtKvMa+NF1
vbgQgEnThi6IHNrLq9F9ttWKc6Tc3qETXGhlYy/cIRdipbrj7CDarFIpqXT+fCe6
o0tVbUL4dQPx8kqAvBvs2TxlvmQ8b1MInvsxsKVJI7KgVMhhqfVBO20d2gzZ9/mt
qTmIbzBGR78aoI4WVM22jg1HCg1ucUixciOBixBMMOM7LIplcBsWSal0gMi8k3ib
rndCFT6+59X4/coi45PCVPrsnsZtgRwvVNcuJ/p5PQuGoWz4Ef/qBnWHt+WIepu0
aUnrHxncxjW0RERK9R+gT/RVCdLXSHNhQhUlCZ/B2bGSVsYX902YZ/JtiiZ7rQvZ
I54OddcaoOJxmng0nI920xDhnnArX6OV5/cyqFvsN9rf8zf/lPzy9uLvjpIKkWFn
4Ka+2ZuoSwYGe4yizZr1hh4Msmr5dwlBzbqCLdCkvbMSXXS647v+SkKVJZtyVQqt
w4khKwT3aVkiW15kRUKOiHyKRmha1LpBTMwkcmWuRc1J3OWa/EiOuRgd+Gsnqcyt
PVt2Cd+wuav5mkFhUMLH4hT4jfufFogQN63er3gxt3GRIPHdPoYQZOzQRzD+wfrI
5VpI69aaVl28OVuTdq0JyY5PpDjf2EtjXnZNR/DysNT6LMh1UCa7yo9vcT2UENnG
Oc+nwsXo/8nqLmDZI6eqTqdlb3ZEUrP7YSVi+IaaMvpgtbAbhq94HLyQDtS39JQr
0MLmVR7P8wR69Ql4V6z/jIQikwWuhV0pV6dpoEmlYetZ47wCMtftzrF/HdIxg3yV
3tDtw4J6eEC0Kt4skCLPlQ==
-----END ENCRYPTED PRIVATE KEY-----
```

```
[01/21/22]seed@VM:~/.../PKI$ openssl rsa  -in ca.key -text -noout
Enter pass phrase for ca.key:
RSA Private-Key: (2048 bit, 2 primes)
modulus:
    00:cc:d1:63:be:67:e7:65:ba:5b:0d:26:6d:b2:39:
    05:53:a8:ab:16:df:30:80:92:a0:bb:79:d6:0c:be:
    ae:a0:1a:5e:f0:f8:e7:5f:30:b3:30:b7:53:45:21:
    76:36:91:66:1d:c5:01:49:d3:d9:63:4b:d3:90:f2:
    0e:cc:18:74:79:79:9a:d4:95:3a:98:e2:f5:da:1c:
    84:ea:bf:c5:8b:4c:7f:61:67:ee:7c:10:c1:65:81:
    e4:f4:22:79:66:05:bd:c2:13:36:fe:07:18:46:0e:
    3e:c9:30:6a:16:90:dc:e8:4f:aa:9d:bb:13:19:91:
    35:d7:24:37:43:07:8b:35:d9:47:47:3a:a4:f3:22:
    02:b4:f8:c7:d9:30:82:17:47:27:4d:c7:48:ff:11:
    17:62:40:7f:95:e7:70:d6:3c:8f:d4:f4:6a:f7:5f:
    6c:28:6a:06:f0:0b:40:18:bf:4d:ed:82:24:1f:87:
    00:e1:3a:23:b6:b8:44:a0:8c:13:bf:83:5b:01:44:
    19:9e:6e:44:ef:25:c1:e3:b6:52:5d:f2:8e:87:ec:
    f0:65:a1:ee:ff:8b:48:d9:b3:0d:85:f5:86:1a:fa:
    0c:5c:5d:d6:12:43:67:b1:f8:24:77:da:17:08:2b:
    87:87:13:83:2f:be:fc:d5:48:47:9a:a5:1d:21:90:
    16:df
publicExponent: 65537 (0x10001)
privateExponent:
    42:16:05:d2:f7:ff:a7:c9:3b:7b:c0:bc:80:56:f9:
    ab:06:af:3d:90:02:3c:5a:13:56:aa:77:30:61:8e:
    42:c6:7f:7f:cd:30:0a:7c:d2:34:93:d2:60:69:ed:
    94:a9:d1:83:25:7f:c6:ec:7e:26:15:df:4b:d3:6e:
    86:d8:15:2c:e4:d9:da:61:d4:28:64:82:e3:3f:74:
    7b:b2:28:f1:4b:5b:86:78:5c:70:d7:8f:2f:4b:7c:
    2e:71:b9:2d:fc:08:40:48:a6:e3:cc:32:3e:d8:75:
    d5:c0:b3:5a:58:9f:8e:ad:b5:e5:72:e9:34:c4:af:
    d4:9d:30:df:85:dd:9b:1f:ce:9a:a2:2d:c7:36:6e:
    cc:54:67:02:d4:ac:db:5e:cc:87:5c:27:32:64:e6:
    84:d8:d9:ff:d9:9d:3e:79:3d:4c:3c:82:e7:fd:01:
    d4:89:8c:3c:c4:98:0c:30:4b:eb:f9:d7:d9:3b:40:
    a7:9e:a3:2a:95:53:7a:be:b7:e6:2d:6d:13:87:57:
    35:d7:07:a0:d2:9b:42:10:aa:47:04:05:d3:b5:6c:
    20:a2:d5:0f:2d:ac:b3:04:c1:3d:c2:87:e9:a5:26:
    5e:a0:2e:5b:05:87:18:3a:4a:05:a0:af:6c:4b:5c:
    f5:5c:07:28:f0:6c:78:a8:a2:4b:fc:ff:51:09:e3:
    d1
prime1:
    00:ea:70:1d:b8:b1:f8:b4:ab:c8:4c:0c:5e:8e:97:
    f0:8c:b7:05:93:f7:ee:20:c3:8a:2c:11:86:8b:3c:
    15:aa:b9:bf:57:d7:7e:ab:8b:0e:9c:a8:3a:cd:53:
    1b:d6:d9:3d:c1:68:b3:65:fc:86:22:90:ee:e6:c8:
    1e:32:c4:34:b2:cb:ec:15:47:3b:5c:f7:e3:30:b6:
    a5:39:aa:5b:b4:44:2b:2e:cd:2e:17:c8:ff:14:7e:
    12:5e:c3:78:9d:d0:0b:e9:8b:4b:c5:7b:21:f4:8e:
    8b:7f:c2:33:46:30:11:59:a6:79:2b:23:56:96:ed:
    69:95:5a:3d:25:3e:1d:50:e5
prime2:
    00:df:a7:dd:5c:19:98:6a:98:f9:3d:06:aa:f8:fe:
    3d:a4:52:08:73:1d:50:6c:71:0e:09:ce:2e:e8:a6:
    e1:c5:4c:18:4b:d9:40:33:63:53:b4:c7:67:99:0a:
    ee:4e:15:7b:09:1d:4e:25:80:02:ed:97:de:d7:a8:
    82:92:a4:9c:2b:b2:0e:d6:65:1e:42:5a:74:ce:aa:
    ff:5e:63:a8:e7:ae:84:f5:d8:7b:b6:a5:a0:53:a1:
    d9:d2:3f:ca:7d:13:bc:9e:fb:50:9e:4a:d0:5c:3c:
    77:ba:d1:13:71:f1:6b:4c:ee:f2:f4:b1:40:99:83:
    91:5f:b4:07:a8:b0:45:c0:73
exponent1:
    0d:45:77:89:43:19:ef:30:62:50:5b:ca:e6:8b:97:
    64:7f:df:e2:f6:80:16:7e:bb:4d:af:58:4c:7d:84:
    44:7b:eb:67:0f:9d:ee:1c:1b:21:a7:2c:5c:ff:3d:
    6e:36:32:16:c6:d4:91:0b:70:94:78:5b:ed:d8:9a:
    4d:09:6a:6a:4c:bc:fa:9f:63:ae:e9:a1:84:da:72:
    14:07:9e:d5:5f:9e:8a:31:b7:50:45:62:9b:48:5f:
    c5:d9:8e:f4:70:18:9c:89:f4:2a:23:c4:52:51:d7:
    77:ce:08:95:0a:97:90:d9:a9:b6:55:73:cb:6b:79:
    34:a9:3d:18:e4:a1:48:39
exponent2:
    68:c1:4f:45:1c:17:ef:95:c6:e7:76:80:0e:2f:c6:
    df:78:2c:cc:fe:25:f5:24:de:d6:68:e4:3f:c4:2a:
    6b:26:c1:1a:85:9f:34:72:89:7a:5b:0b:82:fb:43:
    b2:ff:0c:a9:b0:38:32:08:4b:56:cd:93:6a:9f:5a:
    c9:24:a0:a1:36:bd:0c:5e:40:56:03:d8:42:14:85:
    97:c8:46:0c:7e:09:78:bc:f4:f5:0f:8e:90:9d:76:
    50:ab:e0:43:c5:42:cb:94:1a:a6:89:94:1e:1f:94:
    54:c4:28:bf:6d:bc:3c:44:8f:37:5c:ee:4c:f8:fa:
    d6:40:94:75:c6:5a:65:51
coefficient:
    1d:0a:9a:33:a7:19:5c:7d:e9:44:7d:67:42:8e:88:
    e5:f6:9a:19:09:e9:f3:8a:5c:54:4f:60:2a:60:28:
    e4:e4:f6:e0:98:5c:a5:2d:2a:2b:20:3a:f6:0e:89:
    00:ff:75:a0:5d:19:7a:80:44:fe:11:77:a6:20:88:
    d1:d8:cd:1c:ca:4b:02:85:1f:d9:ef:2b:ac:04:af:
    8b:17:2d:e4:24:e7:47:b3:9f:b7:d5:f2:3e:33:2c:
    77:21:5c:61:69:5c:89:15:c4:52:6c:79:a6:a8:01:
    8b:a0:aa:02:8a:ba:3b:d5:db:02:84:d6:61:5e:3d:
    42:c0:01:d7:f0:c6:5f:61

```

•  What part of the certificate indicates this is a CA’s certificate?  
•  What part of the certificate indicates this is a self-signed certificate?  
•  In the RSA algorithm, we have a public exponent e, a private exponent d, a modulus n, and two secret numbers p and q, such that n=pq.  Please identify the values for these elements in your certificateand key files.