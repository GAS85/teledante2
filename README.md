# teledante2
Simple config for Dante 1.1.19 on Ubuntu 16.04 for Telegram
===============================================
/ Простая настройка Dante 1.1.19 на Ubuntu 16.04 для телеграма 

Features
--------
* Only telegram usage restrictions / Ограничено только телеграмом, выход в интернет заблокирован

Requirements
------------

* Ubuntu 16.04

For nuts
--------

* PayPal https://www.paypal.me/GeorgiySitnikov

Usage / Как пользоваться
-----------------

Simple config for Dante2 1.1.19 on Ubuntu 16.04
based on https://github.com/schors/tgdante2
Only issue that old dante-server Version on Ubuntu 16.04
has different syntax and config should be updated.

Install dante SOCKS5 Proxy server / Устанавливаем пркси сервер
```
sudo apt update & sudo apt install dante-server
```

Add user telegram to group "nogroup" / добавляем пользователя telegram в спец. группу 
```
sudo useradd -s /usr/sbin/nologin -g nogroup telegram && sudo passwd telegram
```

copy config into / копируем конфиг сюда ```/etc/danted.conf``` 

start dante / запускаем прокси сервер
```
sudo service danted start
```
do not forget about correct iptables rules... / не забудте настроить фаервол и открыть нужные порты

Access test / проверка
-----------

console / выполните команду
```
curl --proxy socks5://telegram:PASSWD@192.168.0.2:1080 https://web.telegram.org
```
Приглашаем друзей!
