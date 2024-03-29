# WannaTaco!

```
As we were recovering the data from the computer found in the bunker it was hit with a new strain of ransomware!

We really need the information in this file. Is there anything you can do to help us?

In addition to the encrypted file, we were able to pull a small dump of storage from the filesystem before everything got encrypted. Hope it helps!
```

This was an interesting one!

So at first, I was a bit stumpped as for what to do. The flag.wntco file looks like an encrypted file with a WANNATACO! tag at the beginning and some NULL bytes here and there, and the mem.dmp file looks like it's a PDF document.

After a bit of thinking and searching, I decided to search the mem.dmp for an RSA key. Specifically, looking for the exponent 65537, as that's the most common one. So when I searched for it, I actually found the following in the file!

```
Private-Key: (2048 bit)
modulus:
    00:a2:4c:b1:a3:10:13:bb:47:a3:ce:21:2d:61:a2:
    ff:4c:00:f1:7e:3c:0c:02:bb:a5:34:7a:d5:72:cf:
    0e:a2:7f:f3:91:d6:6b:f9:3d:16:c6:fe:99:91:86:
    61:13:d5:87:eb:0f:d0:7e:f9:8a:bf:0c:ae:49:8e:
    12:db:bd:8b:0f:98:c1:e2:0e:a5:a8:fb:ff:51:d3:
    f3:9e:89:e1:a4:0f:9c:af:f2:76:f1:f3:03:41:6d:
    e3:c2:e4:8d:bc:ab:01:1f:88:80:2e:76:85:ad:84:
    1a:5e:c9:2f:cf:e9:40:8f:46:52:80:c3:50:cc:69:
    54:ab:2d:46:2a:3e:c1:62:9e:f2:da:58:0b:02:fe:
    30:a6:a1:e5:e4:d0:db:29:36:e3:51:f8:75:d7:b2:
    7d:2f:b8:3b:86:21:e1:5a:bc:c5:c2:ff:84:7c:32:
    f5:68:ef:9e:17:3c:0d:d3:75:ca:10:d3:e8:a7:73:
    05:7f:a1:40:df:83:49:57:bb:79:c4:7a:c5:69:89:
    38:68:46:f1:bf:be:1d:94:fc:ed:50:48:00:22:35:
    b1:88:1a:2f:79:2d:06:1e:72:db:71:a3:ce:e5:80:
    91:f2:6f:61:c0:9f:d3:f7:05:bf:80:22:59:a6:95:
    6e:2d:90:f0:c4:c6:77:2a:7e:d1:a2:fe:f9:57:bb:
    32:49
publicExponent: 65537 (0x10001)
privateExponent:
    00:9d:ef:a2:21:7b:40:a8:4b:b3:b4:a0:86:87:ef:
    d5:1e:02:00:ff:05:b1:ee:6a:e9:fe:22:d6:59:ad:
    f2:a0:e1:80:85:d7:b2:24:cd:74:bf:da:fc:58:27:
    fb:8a:10:8d:fe:89:da:2b:e5:ec:45:b4:32:5a:73:
    be:18:45:df:f0:22:87:f1:d2:ad:14:bf:7d:1b:04:
    f5:9a:be:b4:6c:31:a1:19:7b:0a:92:b2:17:e5:f0:
    e8:e6:3c:01:4d:aa:df:21:ef:74:45:42:a3:1d:52:
    63:52:ff:d6:de:2d:2e:dc:fd:e2:c5:58:cb:e4:cf:
    4f:4c:70:77:4a:1e:dd:93:78:69:6d:8f:f1:f3:0e:
    3c:2c:80:4f:29:e4:5a:a1:3f:79:ac:5c:51:41:45:
    39:64:92:36:7a:91:50:2b:3e:c5:40:ff:a6:51:65:
    04:16:1c:59:e5:1e:31:c7:05:ba:30:71:79:2b:8d:
    28:70:c2:86:f0:32:54:51:29:a3:0a:6f:f9:29:13:
    8a:5a:7c:63:34:86:88:03:db:01:83:be:30:d0:e3:
    7a:d4:ec:e7:fc:d3:93:e2:dd:03:68:a6:8a:88:9d:
    15:0f:22:80:19:d2:7c:b2:7c:ea:c2:8c:50:dc:e7:
    fa:32:65:b8:ea:77:19:67:86:b0:86:22:8a:44:55:
    ff:f1
prime1:
    00:b9:18:80:68:d5:32:08:33:0b:2f:09:29:4b:a5:
    bd:92:61:d1:f4:1b:73:e9:45:93:23:a6:fc:80:3e:
    16:a4:c9:6c:f2:b8:a4:33:ee:fd:7c:61:75:19:28:
    df:e2:92:7d:04:15:7c:15:e0:f4:52:f3:71:48:54:
    2b:ba:eb:41:eb:ad:fe:43:8d:e6:5b:82:e3:69:fd:
    84:8e:66:e0:1d:d0:94:26:55:a8:39:af:69:39:53:
    36:87:4d:69:44:4f:4e:c6:c6:2b:66:02:29:0d:77:
    bb:ec:ce:a3:29:82:17:58:f6:93:4e:c3:c2:53:ec:
    35:4e:bd:ef:d3:df:a6:e4:8d
prime2:
    00:e0:78:ad:fb:24:c6:ec:35:72:c5:f5:53:a3:b4:
    c6:58:e8:21:58:9e:d4:c4:63:ce:62:5b:c0:bf:21:
    d8:f3:11:00:d8:03:c3:13:e9:e5:cc:e0:c1:83:54:
    be:ea:65:20:cd:e2:e6:5a:8f:63:d0:44:5a:03:db:
    a2:21:1b:0c:a8:21:48:1b:93:ba:de:97:a9:a0:78:
    8d:ad:19:81:0a:d2:29:66:02:39:84:9d:86:ed:57:
    b1:a0:c2:9e:22:7f:02:b2:87:87:35:f5:99:75:90:
    96:33:da:62:5f:84:26:41:f8:7c:c2:2d:23:a4:14:
    ed:eb:cd:e5:c1:57:6f:7b:ad
exponent1:
    00:ae:40:1b:bb:15:61:d9:88:3c:32:16:9c:d2:c3:
    80:59:0b:4f:fd:4f:ce:ea:3f:7e:8a:a4:cc:b6:ea:
    3c:a4:fb:9f:5e:4d:67:00:21:30:6f:e4:cb:b9:58:
    da:94:51:35:f2:1f:4b:c6:c9:15:19:f6:66:a2:21:
    e3:5d:3f:d6:ba:49:fd:c1:99:17:d0:f4:c2:a4:e8:
    6e:df:24:88:3e:69:3a:df:6f:ea:44:0c:17:b2:48:
    dd:5f:b9:07:ad:b0:3f:c8:2f:8d:71:a5:fd:01:d9:
    c3:87:e6:ec:81:ca:1f:b2:b7:c6:eb:f2:ac:c2:16:
    f0:04:66:19:1e:4c:41:b0:8d
exponent2:
    00:a2:db:6b:7e:d6:83:ec:44:2a:ed:2c:bc:6d:fd:
    6e:1a:7a:f0:16:97:c5:ce:66:8b:0a:19:7f:92:2c:
    40:76:b9:53:5f:65:fb:56:ab:50:2a:80:b6:65:4e:
    4a:e5:4c:51:ac:8e:7e:8a:1d:96:51:38:06:06:de:
    86:96:76:45:8c:85:f9:06:e8:fb:9f:1b:71:da:17:
    1c:d3:05:b9:f5:db:dc:65:42:1f:f0:f3:49:3d:51:
    6e:72:30:41:02:ce:1b:6a:e3:a1:59:a8:c2:99:e5:
    38:d4:8e:10:e9:33:bb:7e:09:86:9a:6a:9d:7d:22:
    22:2b:fe:ca:3e:a7:ed:1e:51
coefficient:
    01:e1:ab:a8:a0:95:5b:02:66:d0:fc:d8:54:48:48:
    ec:3d:67:02:30:fa:51:6c:40:0e:6d:1b:11:06:de:
    e2:5b:21:78:5b:ae:9f:a9:e4:4b:e9:e2:b6:7e:f4:
    0c:5f:b5:2b:be:3d:ae:09:73:49:34:5b:fa:6b:d2:
    76:d2:61:37:70:a6:99:be:0d:54:7a:33:f8:6f:c3:
    1d:cc:db:31:9f:b9:c5:8a:fa:45:15:4f:4b:dd:3d:
    c3:83:13:6a:23:f0:3c:34:35:a4:dc:22:9b:24:01:
    e9:c7:6f:44:18:59:60:9d:4f:2c:bc:a8:2e:84:3e:
    6e:b8:65:b6:01:dc:c5:95
```

The text output of an RSA private key! That seems promising! I then converted that to an OpenSSL PEM file (a bit of work to convert it from the text representation, but not too hard).

But I'm still not there yet, I have to decrypt the file now. RSA typically works by generating an AES key, encrypting the data with the AES key, then encrypting the AES key with the RSA key. 

I ended up finding the encrypted AES key in the file by guessing/assuming what it had to be, but if you take a look at https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html you'll see that the WannaCry file format is as such:

```
struct T_WNRY {
    char magic[8]; // must match WANACRY!
    uint32_t enc_keylen; // needs to be 0x100
    char enc_key[enc_keylen];
    uint32_t unknown; // was 4
    uint64_t enc_datalen;
    char enc_data[enc_data_len];
}
```

So that means that the encrypted AES key is the following:

```
39814720 558BAFAB 1EE588C8 63851E3C
4AD702AE 85C4066D 6A0F217D 019F08EF
695F5AF2 0FF30D48 E62D771F 27ACDD98
1D8FDD87 7C70F107 D68F613E B732980F
29BB3683 99916898 33C195C4 BEDED132
09C32469 A5F29442 F06A59EA 680EB60C
58D45A2A 6FEA9C92 579FBFEC 835063C3
A38A6A9B 56866EB4 785EA0C8 27830644
7D773999 6E1CDD59 3426E820 71420219
D34892B1 5CDD258C AEE9BDAA 92DBDAB4
6BC7E03F 2578FC7B 610B08B3 09A6FCCC
6DFA25B2 450E9EAB 0D11EA67 3C0F0343
62CAC9CA 1A7124F3 2FA804B4 78CB41F4
A9BBA0D1 5472CD4D 95CE014F B7E5912F
952C6D48 07163107 CE71E583 E9C089A9
45F77A30 F30C313D CD842910 78204F5E
```

Running that data through an OpenSSL decrypt with the private key that we had found earlier resulted in the following AES key (well, there were a lot of leading NULL bytes, followed by these 16 bytes):

```
C29E5EF6 D88A7E28 C62E4E56 008F0AB8
```

Progress!

so, that's 16 bytes, which is the size of an AES-128 key. But, we sill don't know wht algorithm is used or what the IV is. However, reading further on that website, I found that "The files are encrypted with a randomly generated 128-bit AES key in CBC mode with a NULL initialization vector." That's great! Lets give it a try!

So I copied the contents starting at 0x11A and going to the end of the file into a new bin file and executed the following OpenSSL command.

```
openssl enc -d -nosalt -aes-128-cbc -in flag.wntco_stripped.bin -out flag_dec1.bin  -K C29E5EF6D88A7E28C62E4E56008F0AB8 -iv 00000000000000000000000000000000
```

Which resulted in an output "flag_dec1.bin" that looked like a JPEG file! Opening the JPEG file, I received the following:

```
Tacocon{TacosAreTheBest_ThankfullyYouWereAbleToBeatThisRansomware!}
```
