# x

## rpm

```sh
$ rpm -qa | less
...
$ rpm -qa sys*
syslinux-4.05-13.el7.x86_64
sysvinit-tools-2.88-14.dsf.el7.x86_64
sysstat-10.1.5-11.el7.x86_64
systemd-libs-219-30.el7_3.9.x86_64
systemd-sysv-219-30.el7_3.9.x86_64
systemtap-runtime-3.0-7.el7.x86_64
systemd-python-219-30.el7_3.9.x86_64
systemd-219-30.el7_3.9.x86_64
```

```sh
$ rpm -qf $( which gethostip )
syslinux-4.05-13.el7.x86_64
$
$ rpm -q syslinux
syslinux-4.05-13.el7.x86_64
$
$ rpm -qi syslinux
Name        : syslinux
Version     : 4.05
Release     : 13.el7
Architecture: x86_64
...
$
$ rpm -q httpd
httpd-2.4.6-45.el7.centos.4.x86_64
$
$ rpm -ql httpd
/etc/httpd
/etc/httpd/conf
/etc/httpd/conf.d
/etc/httpd/conf.d/README
/etc/httpd/conf.d/autoindex.conf
/etc/httpd/conf.d/userdir.conf
/etc/httpd/conf.d/welcome.conf
/etc/httpd/conf.modules.d
...
$
$ rpm -qc httpd
/etc/httpd/conf.d/autoindex.conf
/etc/httpd/conf.d/userdir.conf
/etc/httpd/conf.d/welcome.conf
/etc/httpd/conf.modules.d/00-base.conf
/etc/httpd/conf.modules.d/00-dav.conf
/etc/httpd/conf.modules.d/00-lua.conf
/etc/httpd/conf.modules.d/00-mpm.conf
/etc/httpd/conf.modules.d/00-proxy.conf
/etc/httpd/conf.modules.d/00-systemd.conf
/etc/httpd/conf.modules.d/01-cgi.conf
/etc/httpd/conf/httpd.conf
/etc/httpd/conf/magic
/etc/logrotate.d/httpd
/etc/sysconfig/htcacheclean
/etc/sysconfig/httpd
$
$ rpm -q --changelog httpd | less
...
$
% rpm -qR docker-ce | sort -ur
xz
tar
systemd-units
rtld(GNU_HASH)
rpmlib(PayloadIsXz) <= 5.2-1
...
```

```sh
sudo rpm -ivH https://..../xxxx.rpm
sudo rpm -UvH https://..../xxxx.rpm
```

```sh
sudo rpm -e httpd
sudo rpm -e --nodeps httpd
```

```sh
$ rpm2cpio httpd-tools-2.4.6-80.el7.centos.x86_64.rpm | cpio -t
./usr/bin/ab
./usr/bin/htdbm
./usr/bin/htdigest
./usr/bin/htpasswd
./usr/bin/httxt2dbm
./usr/bin/logresolve
./usr/share/doc/httpd-tools-2.4.6
./usr/share/doc/httpd-tools-2.4.6/LICENSE
./usr/share/doc/httpd-tools-2.4.6/NOTICE
./usr/share/man/man1/ab.1.gz
./usr/share/man/man1/htdbm.1.gz
./usr/share/man/man1/htdigest.1.gz
./usr/share/man/man1/htpasswd.1.gz
./usr/share/man/man1/httxt2dbm.1.gz
./usr/share/man/man1/logresolve.1.gz
342 blocks
$
$ rpm2cpio httpd-tools-2.4.6-80.el7.centos.x86_64.rpm | cpio -t *htdigest*
./usr/bin/htdigest
./usr/share/man/man1/htdigest.1.gz
342 blocks
$
$ rpm2cpio httpd-tools-2.4.6-80.el7.centos.x86_64.rpm | cpio -idmv */htdigest
./usr/bin/htdigest
$
$ ls ./usr/bin/htdigest
./usr/bin/htdigest
342 blocks
```

## yum

```sh
$ yum search --enablerepo=epel pv | grep "^pv"
pv.x86_64 : A tool for monitoring the progress of data through a pipeline
$
$ sudo yum install --enablerepo=epel pv
$ sudo yum install https://..../xxxx.rpm
$
$ sudo yum update -y
```

```sh
sudo yum remove httpd
```

### docker-ce

```sh
$ sudo yum -y install epel-release \
  && sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo \
  && sudo yum -y install docker-ce \
  && sudo systemctl start docker \
  && sudo systemctl enable $_ \
  && sudo docker ps -a \
  && sudo docker pull centos:7 \
  && sudo docker images
```
