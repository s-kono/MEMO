
```sh
./config --prefix=/hoge/fuga/openssl-1.1.1t shared zlib \
&& make \
&& make install; echo $?
ln -svnf openssl-1.1.1 /hoge/fuga/openssl-1.1.1t
```

## CentOS 7

```sh
TMPDIR=/var/tmp/ \
  LDFLAGS="-Wl,-rpath /hoge/fuga/openssl-1.1.1/lib" \
  CONFIGURE_OPTS="--with-openssl=/hoge/fuga/openssl-1.1.1" \
  pyenv install 3.11.2
```

```sh
./configure \
  --prefix=/hoge/fuga/python-3.11.2 \
  LDFLAGS="-Wl,-rpath /hoge/fuga/openssl-1.1.1/lib" \
  --with-openssl=/hoge/fuga/openssl-1.1.1 \
  --enable-optimizations \
&& make \
&& make install \
&& /hoge/fuga/python-3.11.2/bin/python3 -c 'import ssl,sys; print(sys.version)'; echo $?
```
