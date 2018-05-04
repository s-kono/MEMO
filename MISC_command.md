
### curl

```sh
$ curl --header "Host: www.example.com" http://10.0.1.2/
$ curl --resolve www.example.com:80:10.0.1.2 http://www.example.com/
$ curl --compressed --retry 2 --retry-delay 30 --max-time 10 -sSL -A "${UserAgent}" http://www.example.jp/
$ curl -c ${cookie} -b ${cookie} -o ${output} -sSk https://localhost/
$ curl -sS -O http://localhost/123.txt
```


### dmidecode

```sh
$ sudo dmidecode
$ sudo dmidecode -t processor
$ sudo dmidecode -t memory
```


### gethostip


```sh
$ gethostip 10.0.3.100
10.0.3.100 10.0.3.100 0A000364
$ gethostip -x 10.0.3.100
0A000364
$
$ gethostip www.example.com
www.example.com 93.184.216.34 5DB8D822
$ gethostip -x www.example.com
5DB8D822
$ echo 5DB8D822 | perl -pe 's/(..)/$1\n/g' | while read a; do echo "obase=10; ibase=16; ${a}" | bc; done | perl -pe 's/\n/./' | sed 's/.$//'; echo
93.184.216.34
$
$ dig +short amazon.com
205.251.242.103
176.32.98.166
176.32.103.205
$ gethostip -d amazon.com
205.251.242.103
$
$ dig +short www.amazon.com
www.cdn.amazon.com.
d3ag4hukkh62yn.cloudfront.net.
13.33.215.239
$ gethostip -d www.amazon.com
13.33.215.239
```


### ldapsearch

```sh
$ ldapsearch -LLL -H ldap://ldap.example.jp/ -x -b 'ou=People,dc=hoge,dc=example,dc=net' uid=admin
$ ldapsearch -LLL -x -W -b 'dc=hoge,dc=example,dc=net' uidNumber=1001 uid
$ ldapsearch -LLL -x -b 'ou=Group,dc=hoge,dc=example,dc=net' 'cn=SuperAdmin' memberUid
```


### nmap

```sh
$ nmap -sP 10.0.0.0/25
$ nmap -sS -P0 -r -p 1-65535 --min-hostgroup 256 ${addrs}
$ nmap -sT -P0 -r -p 1-65535 --min-hostgroup 256 ${addrs}
$ nmap -sU -P0 -r -p 1-65535 --min-hostgroup 256 ${addrs}
```


### snmp

```sh
$ snmptranslate -On IF-MIB::ifEntry
.1.3.6.1.2.1.2.2.1
$ snmptranslate -On IF-MIB::ifXEntry
.1.3.6.1.2.1.31.1.1.1
$ snmptranslate -On UCD-SNMP-MIB::prEntry
.1.3.6.1.4.1.2021.2.1
$ snmptranslate .1.3.6.1.4.1.2021.2.1
UCD-SNMP-MIB::prEntry
$ snmptranslate .1.3.6.1.4.1.2021.2
UCD-SNMP-MIB::prTable
```

```sh
$ snmpbulkwalk -v2c -c ${community} localhost system
$ snmpbulkwalk -v2c -c ${community} localhost IF-MIB::ifEntry
$ snmpbulkwalk -v2c -c ${community} localhost HOST-RESOURCES-MIB::hrStorage
$ snmpbulkwalk -v2c -c ${community} localhost UCD-SNMP-MIB::extEntry
```


### ssh

```sh
$ ssh -gL 13389:windows.local:3389 -p 1022 user@home.local
$ ssh -oConnectTimeout=15 -oBatchMode=yes -oStrictHostKeyChecking=no -oUserKnownHostsFile=/dev/null -oCheckHostIP=no common.local
```


### MISC

```sh
$ LANG=C /bin/df --portability
```


