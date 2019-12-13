<h2>Установка и настройка подключение Ejabberd 16.01 по VPN к удаленным серверам, с централизованным хранением сообщений пользователей в и личных карт БД Mysql</h2>


Установка производится на ОС Ubuntu 16.04:

Загружаем пакет с официального сайта https://www.process-one.net/en/ejabberd/downloads/

или:

1) **`sudo apt update`**  - обновляем информацию о репозиториях
---
2) **`sudo apt-get install ejabberd`** - устанавливаем с репозитрия ubuntu - ejabebrd
---
3) **`sudo apt-get install erlang-p1-mysql`** - важный пакет erlang для работы с DB Mysql
---
4) **`sudo service ejabberd stop`** - останавливаем сервис для дальнейшей конфигурации
---

На Ubuntu 16.04 и ниже - Не выполнять apt update!


