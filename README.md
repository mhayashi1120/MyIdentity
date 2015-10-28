# My public keys

Language: Japanese (English)
林雅博 (Hayashi Masahiro)

http://mhayashi1120.net/

https://github.com/mhayashi1120

https://twitter.com/mhayashi1120

https://www.facebook.com/mhayashi1120

http://www.hatena.ne.jp/mhayashi1120/

## GPG public key

1. clone the git repository.
2. move to the cloned repository.
3. execute the following command.

```
gpg --import gpg/key.txt
```

## SSL Root Certificate

Fingerprint for ca.mhayashi1120.net
SHA1 Fingerprint=5E:9A:D6:31:92:B5:54:A1:CE:FF:DB:73:21:73:8A:FA:7C:43:4A:4A
SHA256 Fingerprint=D1:C2:81:9A:7C:54:98:8F:CF:7A:17:32:07:C9:E7:FD:1A:B2:5E:EF:1F:58:5E:FE:44:85:D8:02:31:8A:CC:45
SHA512 Fingerprint=51:84:85:16:A2:F0:96:3A:1B:78:EB:49:3E:69:37:88:BB:C5:36:A4:A4:C7:EC:40:69:C0:DB:01:51:04:97:F1:49:73:FF:47:9B:77:71:67:7A:AA:E8:25:DA:2C:9A:86:CF:11:10:82:C7:EC:B7:94:14:06:DB:B1:86:6B:60:32


### Windows

___TODO how to import___

### Linux

```
echo "deb http://mhayashi1120.net/apt/ ./" | sudo tee /etc/apt/sources.list.d/mhayashi1120.list

sudo aptitude update && sudo aptitude install mhayashi1120-ca-certificate
```

### Android


