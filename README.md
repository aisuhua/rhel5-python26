# RHEL5 Install Python 2.6

```sh
# Install Build Requirements
yum install gcc gdbm-devel readline-devel ncurses-devel zlib-devel \
  bzip2-devel sqlite-devel db4-devel openssl-devel tk-devel bluez-libs-devel

# Compile Python
VERSION=2.6.1
mkdir ~/src
cd ~/src
wget http://python.org/ftp/python/$VERSION/Python-$VERSION.tar.bz2
tar xjf Python-$VERSION.tar.bz2
rm Python-$VERSION.tar.bz2
cd Python-$VERSION
./configure --enable-ipv6 --prefix=/opt
make
sudo make install
```

如果你在下载 Python 安装包时报以下错误，可以使用本仓库的包或者自行先下载后再上传到服务器

```sh
[root@localhost ~]# wget http://python.org/ftp/python/2.6.1/Python-2.6.1.tar.bz2
--2023-12-25 23:09:46--  http://python.org/ftp/python/2.6.1/Python-2.6.1.tar.bz2
Resolving python.org... 151.101.128.223, 151.101.64.223, 151.101.0.223, ...
Connecting to python.org|151.101.128.223|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://www.python.org/ftp/python/2.6.1/Python-2.6.1.tar.bz2 [following]
--2023-12-25 23:09:46--  https://www.python.org/ftp/python/2.6.1/Python-2.6.1.tar.bz2
Resolving www.python.org... 151.101.108.223, 2a04:4e42:1a::223
Connecting to www.python.org|151.101.108.223|:443... connected.
OpenSSL: error:140770FC:SSL routines:SSL23_GET_SERVER_HELLO:unknown protocol
```

参考链接

- [Installing Python 2.6 in CentOS 5 (or RHEL5)](https://bda.ath.cx/blog/2009/04/08/installing-python-26-in-centos-5-or-rhel5/)
