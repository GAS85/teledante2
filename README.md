# teledante2
Simple config for Dante2 1.1.19 on Ubuntu 16.04
===============================================

Features
--------
* Only telegram usage restrictions

Requirements
------------

* Ubuntu 16.04

For nuts
--------

* PayPal https://www.paypal.me/GeorgiySitnikov

Usage
-----------------

Simple config for Dante2 1.1.19 on Ubuntu 16.04
based on https://github.com/schors/tgdante2
Only issue that old dante-server Version on Ubuntu 16.04
has different syntax and config should be updated.

Install dante SOCKS5 Proxy server
```
sudo apt update & sudo apt install dante-server
```

Add user telegram:
```
sudo useradd -s /usr/sbin/nologin telegram & sudo passwd telegram
```

copy config into ```/etc/danted.conf```

start dante
```
sudo service danted start
```
do not forget about correct iptables rules...

Access test
-----------

```console
curl --proxy socks5://telegram:PASSWD@192.168.0.2:1080 https://web.telegram.org
```
