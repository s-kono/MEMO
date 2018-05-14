

| 数値文字参照(10進) | URLエンコード(16進) | 記号 | 文字実体参照 |
|---|---|---|---|
|   |   |   |   |
| &amp;#32; | %20 | スペース | |
| &amp;#33; | %21 | ! | |
| &amp;#34; | %22 | " | &amp;quot; |
| &amp;#35; | %23 | # | |
| &amp;#36; | %24 | $ | |
| &amp;#37; | %25 | % | |
| &amp;#38; | %26 | & | &amp;amp; |
| &amp;#39; | %27 | ' | |
| &amp;#40; | %28 | ( | |
| &amp;#41; | %29 | ) | |
| &amp;#42; | %2A | * | |
| &amp;#43; | %2B | + | |
| &amp;#44; | %2C | , | |
| &amp;#45; | %2D | - | |
| &amp;#46; | %2E | . | |
| &amp;#47; | %2F | / | |
|   |   |   |   |
| &amp;#58; | %3A | : | |
| &amp;#59; | %3B | ; | |
| &amp;#60; | %3C | < | &amp;lt; |
| &amp;#61; | %3D | = | |
| &amp;#62; | %3E | > | &amp;gt; |
| &amp;#63; | %3F | ? | |
| &amp;#64; | %40 | @ | |
|   |   |   |   |
| &amp;#91; | %5B | [ | |
| &amp;#92; | %5C | \ | |
| &amp;#93; | %5D | ] | |
| &amp;#94; | %5E | ^ | |
| &amp;#95; | %5F | _ | |
| &amp;#96; | %60 | ` | |


### 16 進ダンプ

```sh
$ cat /etc/hosts | hexdump -C
00000000  31 32 37 2e 30 2e 30 2e  31 20 20 20 6c 6f 63 61  |127.0.0.1   loca|
00000010  6c 68 6f 73 74 20 6c 6f  63 61 6c 68 6f 73 74 2e  |lhost localhost.|
00000020  6c 6f 63 61 6c 64 6f 6d  61 69 6e 20 6c 6f 63 61  |localdomain loca|
00000030  6c 68 6f 73 74 34 20 6c  6f 63 61 6c 68 6f 73 74  |lhost4 localhost|
00000040  34 2e 6c 6f 63 61 6c 64  6f 6d 61 69 6e 34 0a 3a  |4.localdomain4.:|
00000050  3a 31 20 20 20 20 20 20  20 20 20 20 20 20 20 20  |:1              |
00000060  20 20 20 20 20 20 20 20  20 20 20 20 20 20 20 20  |                |
00000070  20 20 20 20 20 20 20 20  20 20 20 6c 6f 63 61 6c  |           local|
00000080  68 6f 73 74 36 20 6c 6f  63 61 6c 68 6f 73 74 36  |host6 localhost6|
00000090  2e 6c 6f 63 61 6c 64 6f  6d 61 69 6e 36 0a        |.localdomain6.|
0000009e
$
$ cat /etc/hosts | od -Ax -t x1z
000000 31 32 37 2e 30 2e 30 2e 31 20 20 20 6c 6f 63 61  >127.0.0.1   loca<
000010 6c 68 6f 73 74 20 6c 6f 63 61 6c 68 6f 73 74 2e  >lhost localhost.<
000020 6c 6f 63 61 6c 64 6f 6d 61 69 6e 20 6c 6f 63 61  >localdomain loca<
000030 6c 68 6f 73 74 34 20 6c 6f 63 61 6c 68 6f 73 74  >lhost4 localhost<
000040 34 2e 6c 6f 63 61 6c 64 6f 6d 61 69 6e 34 0a 3a  >4.localdomain4.:<
000050 3a 31 20 20 20 20 20 20 20 20 20 20 20 20 20 20  >:1              <
000060 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20  >                <
000070 20 20 20 20 20 20 20 20 20 20 20 6c 6f 63 61 6c  >           local<
000080 68 6f 73 74 36 20 6c 6f 63 61 6c 68 6f 73 74 36  >host6 localhost6<
000090 2e 6c 6f 63 61 6c 64 6f 6d 61 69 6e 36 0a        >.localdomain6.<
00009e
$
$  cat /etc/hosts | od -Ax -t x1c
000000  31  32  37  2e  30  2e  30  2e  31  20  20  20  6c  6f  63  61
         1   2   7   .   0   .   0   .   1               l   o   c   a
000010  6c  68  6f  73  74  20  6c  6f  63  61  6c  68  6f  73  74  2e
         l   h   o   s   t       l   o   c   a   l   h   o   s   t   .
000020  6c  6f  63  61  6c  64  6f  6d  61  69  6e  20  6c  6f  63  61
         l   o   c   a   l   d   o   m   a   i   n       l   o   c   a
000030  6c  68  6f  73  74  34  20  6c  6f  63  61  6c  68  6f  73  74
         l   h   o   s   t   4       l   o   c   a   l   h   o   s   t
000040  34  2e  6c  6f  63  61  6c  64  6f  6d  61  69  6e  34  0a  3a
         4   .   l   o   c   a   l   d   o   m   a   i   n   4  \n   :
000050  3a  31  20  20  20  20  20  20  20  20  20  20  20  20  20  20
         :   1
000060  20  20  20  20  20  20  20  20  20  20  20  20  20  20  20  20

000070  20  20  20  20  20  20  20  20  20  20  20  6c  6f  63  61  6c
                                                     l   o   c   a   l
000080  68  6f  73  74  36  20  6c  6f  63  61  6c  68  6f  73  74  36
         h   o   s   t   6       l   o   c   a   l   h   o   s   t   6
000090  2e  6c  6f  63  61  6c  64  6f  6d  61  69  6e  36  0a
         .   l   o   c   a   l   d   o   m   a   i   n   6  \n
00009e
$
$ cat /etc/hosts | od -Ax -t x1cz
000000  31  32  37  2e  30  2e  30  2e  31  20  20  20  6c  6f  63  61
         1   2   7   .   0   .   0   .   1               l   o   c   a  >127.0.0.1   loca<
000010  6c  68  6f  73  74  20  6c  6f  63  61  6c  68  6f  73  74  2e
         l   h   o   s   t       l   o   c   a   l   h   o   s   t   .  >lhost localhost.<
000020  6c  6f  63  61  6c  64  6f  6d  61  69  6e  20  6c  6f  63  61
         l   o   c   a   l   d   o   m   a   i   n       l   o   c   a  >localdomain loca<
000030  6c  68  6f  73  74  34  20  6c  6f  63  61  6c  68  6f  73  74
         l   h   o   s   t   4       l   o   c   a   l   h   o   s   t  >lhost4 localhost<
000040  34  2e  6c  6f  63  61  6c  64  6f  6d  61  69  6e  34  0a  3a
         4   .   l   o   c   a   l   d   o   m   a   i   n   4  \n   :  >4.localdomain4.:<
000050  3a  31  20  20  20  20  20  20  20  20  20  20  20  20  20  20
         :   1                                                          >:1              <
000060  20  20  20  20  20  20  20  20  20  20  20  20  20  20  20  20
                                                                        >                <
000070  20  20  20  20  20  20  20  20  20  20  20  6c  6f  63  61  6c
                                                     l   o   c   a   l  >           local<
000080  68  6f  73  74  36  20  6c  6f  63  61  6c  68  6f  73  74  36
         h   o   s   t   6       l   o   c   a   l   h   o   s   t   6  >host6 localhost6<
000090  2e  6c  6f  63  61  6c  64  6f  6d  61  69  6e  36  0a
         .   l   o   c   a   l   d   o   m   a   i   n   6  \n          >.localdomain6.<
00009e
$
$ cat /etc/hosts | xxd -g 1
0000000: 31 32 37 2e 30 2e 30 2e 31 20 20 20 6c 6f 63 61  127.0.0.1   loca
0000010: 6c 68 6f 73 74 20 6c 6f 63 61 6c 68 6f 73 74 2e  lhost localhost.
0000020: 6c 6f 63 61 6c 64 6f 6d 61 69 6e 20 6c 6f 63 61  localdomain loca
0000030: 6c 68 6f 73 74 34 20 6c 6f 63 61 6c 68 6f 73 74  lhost4 localhost
0000040: 34 2e 6c 6f 63 61 6c 64 6f 6d 61 69 6e 34 0a 3a  4.localdomain4.:
0000050: 3a 31 20 20 20 20 20 20 20 20 20 20 20 20 20 20  :1
0000060: 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
0000070: 20 20 20 20 20 20 20 20 20 20 20 6c 6f 63 61 6c             local
0000080: 68 6f 73 74 36 20 6c 6f 63 61 6c 68 6f 73 74 36  host6 localhost6
0000090: 2e 6c 6f 63 61 6c 64 6f 6d 61 69 6e 36 0a        .localdomain6.
$
$ cat /etc/hosts | xxd -g 1 -u
0000000: 31 32 37 2E 30 2E 30 2E 31 20 20 20 6C 6F 63 61  127.0.0.1   loca
0000010: 6C 68 6F 73 74 20 6C 6F 63 61 6C 68 6F 73 74 2E  lhost localhost.
0000020: 6C 6F 63 61 6C 64 6F 6D 61 69 6E 20 6C 6F 63 61  localdomain loca
0000030: 6C 68 6F 73 74 34 20 6C 6F 63 61 6C 68 6F 73 74  lhost4 localhost
0000040: 34 2E 6C 6F 63 61 6C 64 6F 6D 61 69 6E 34 0A 3A  4.localdomain4.:
0000050: 3A 31 20 20 20 20 20 20 20 20 20 20 20 20 20 20  :1
0000060: 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
0000070: 20 20 20 20 20 20 20 20 20 20 20 6C 6F 63 61 6C             local
0000080: 68 6F 73 74 36 20 6C 6F 63 61 6C 68 6F 73 74 36  host6 localhost6
0000090: 2E 6C 6F 63 61 6C 64 6F 6D 61 69 6E 36 0A        .localdomain6.
```


### URL エンコード / デコード

```sh
$ echo -n あいうえお | nkf -WwMQ | tr = %; echo
%E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A
$
$ echo -n あいうえお | jq -s -R -r @uri
%E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A
$
$ echo -n あいうえお | ruby -r uri -ne 'print URI.escape $_'; echo
%E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A
$
$ curl -vsS http://localhost/api-get  -d "a=1" --data-urlencode "word=あいうえお" --get 2>&1 | grep "> .*HTTP"
> GET /api?a=1&word=%E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A HTTP/1.1
$
$ curl -vsS http://localhost/api-post -d "a=1" --data-urlencode "word=あいうえお"       2>&1 | grep "> .*HTTP"
> POST /api-post HTTP/1.1
$
$ curl -s '' -d "a=1" --data-urlencode "word=あいうえお" --get -w '%{url_effective}\n'
/?a=1&word=%E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A
```

```sh
$ echo -n %E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A | nkf --url-input; echo
あいうえお
$
$ echo -n %E3%81%82%E3%81%84%E3%81%86%E3%81%88%E3%81%8A | ruby -r uri -ne 'print URI.unescape $_'; echo
あいうえお
```

