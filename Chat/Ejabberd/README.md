<h2>Установка и настройка подулючения Ejabberd 16.01 по VPN у удаленным серверам</h2>


Установка производится на ОС Ubuntu 16.04:

Загружаем пакет с официального сайта https://www.process-one.net/en/ejabberd/downloads/

или:

1) **`sudo apt update`**  - обновляем информацию о репозиториях
--
2) **`sudo apt-get install ejabberd`**
---
3) **`sudo apt-get install erlang-p1-mysql`** - важный пакет erlang для работы с DB Mysql!
---
4) **`sudo service ejabberd stop`**
---

На Ubuntu 16.04 и ниже - Не выполнять apt update!
