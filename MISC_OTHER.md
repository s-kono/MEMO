

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

