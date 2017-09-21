openssl + ARIA algoritm example
===

1. git clone from openssl source
```bash
git clone https://github.com/openssl/openssl.git
```

2. build wihtout non-free algoritm
```bash
./Configure no-idea no-md2 no-mdc2 no-rc5 no-rc4 enable-aria
make depend && make
make test
sudo make install
```

3. aes sample

* build
```bash
gcc aes.c -o aes -L/usr/local/lib -lssl -lcrypto
```
* output
```
Ciphertext is:
0000 - e0 6f 63 a7 11 e8 b7 aa-9f 94 40 10 7d 46 80 a1   .oc.......@.}F..
0010 - 17 99 43 80 ea 31 d2 a2-99 b9 53 02 d4 39 b9 70   ..C..1....S..9.p
0020 - 2c 8e 65 a9 92 36 ec 92-07 04 91 5c f1 a9 8a 44   ,.e..6.....\...D
Decrypted text is:
The quick brown fox jumps over the lazy dog
```
4. aria example

* build
```bash
gcc aria.c -o aria -L/usr/local/lib -lssl -lcrypto
```
* output
```
Ciphertext is:
0000 - cd 09 81 3e 8c 2d 3a f5-9f fa b7 54 62 3b be fe   ...>.-:....Tb;..
0010 - c0 1e 17 0f a3 82 94 f7-ee 31 a5 6d ab d1 55 ec   .........1.m..U.
0020 - b3 03 3c a2 3c 29 7e 92-4a e2 4d 0c c0 2c de 46   ..<.<)~.J.M..,.F
Decrypted text is:
The quick brown fox jumps over the lazy dog
```