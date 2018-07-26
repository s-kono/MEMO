# xx

## xxx

### 構文チェック

```sh
script=test.py
python -m py_compile ${script} && rm ${script}c
```

## python3

* RHEL 7.5 で Python 2.7 が deprecated になりました - methaneのブログ
  * <https://methane.hatenablog.jp/entry/2018/04/11/RHEL_7.5_%E3%81%A7_Python_2.7_%E3%81%8C_deprecated_%E3%81%AB%E3%81%AA%E3%82%8A%E3%81%BE%E3%81%97%E3%81%9F>

> Ubuntu 18.04 LTS では main リポジトリから Python 2.7 を排除するのが間に合わなかったのですが...

* python3 は RHEL 7 でサポートされますか?
  * <https://access.redhat.com/ja/solutions/2994241>

* Bionic (18.04) : python2.7 package : Ubuntu
  * <https://launchpad.net/ubuntu/bionic/+source/python2.7>

### pip

* <https://pip.pypa.io/en/latest/installing/>

> pip is already installed if you are using Python 2 >=2.7.9 or Python 3 >=3.4 downloaded from python.org or if you are working in a Virtual Environment created by virtualenv or pyvenv.

### CentOS7

```sh
$ yum search --enablerepo=epel python3 | grep -P "^python3\d*\."
python34.x86_64 : Version 3 of the Python programming language aka Python 3000
python36.x86_64 : Interpreter of the Python programming language
$
$ sudo yum install --enablerepo=epel -y python36
$ type python3
python3 not found
$
$ ls -l /bin/python3* /usr/bin/python3*
-rwxr-xr-x 2 root root 11328 2018-01-05 01:43 /bin/python3.6*
-rwxr-xr-x 2 root root 11328 2018-01-05 01:43 /bin/python3.6m*
lrwxrwxrwx 1 root root    18 2018-05-06 19:47 /bin/python36 -> /usr/bin/python3.6*
-rwxr-xr-x 2 root root 11328 2018-01-05 01:43 /usr/bin/python3.6*
-rwxr-xr-x 2 root root 11328 2018-01-05 01:43 /usr/bin/python3.6m*
lrwxrwxrwx 1 root root    18 2018-05-06 19:47 /usr/bin/python36 -> /usr/bin/python3.6*
```

### Ubuntu16.04

```sh
$ ls -l /usr/bin/python* | grep -v config
lrwxrwxrwx 1 root root       9 2017-11-24 09:52 /usr/bin/python -> python2.7
lrwxrwxrwx 1 root root       9 2017-11-24 09:52 /usr/bin/python2 -> python2.7
-rwxr-xr-x 1 root root 3492656 2017-12-05 03:14 /usr/bin/python2.7
lrwxrwxrwx 1 root root       9 2018-01-17 07:01 /usr/bin/python3 -> python3.5
-rwxr-xr-x 2 root root 4464400 2017-11-29 01:53 /usr/bin/python3.5
-rwxr-xr-x 2 root root 4464400 2017-11-29 01:53 /usr/bin/python3.5m
lrwxrwxrwx 1 root root      10 2018-01-17 07:01 /usr/bin/python3m -> python3.5m
```

### 2 to 3 変換

```sh
$ 2to3 ${script}
$ 2to3 -w ${script}
   -w, --write           Write back modified files
```

### スタイルチェック

    pep8 has been renamed to pycodestyle (GitHub issue #466)
    Use of the pep8 tool will be removed in a future release.

* <https://github.com/PyCQA/pycodestyle/issues/466>

```sh
$ sudo pip3 install pyflakes
$ sudo pip3 install pycodestyle
$ pyflakes ${script}
$ pycodestyle ${script}
$ pycodestyle --ignore=E221,E501 ${script}
   --ignore=errors      skip errors and warnings
```

* flake8
