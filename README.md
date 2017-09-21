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
