<h2>Установка и настройка подключения Ejabberd 16.01 по VPN к удаленным серверам, с централизованным хранением сообщений пользователей и личных карт БД Mysql</h2>


Установка производится на ОС Ubuntu 16.04:

Загружаем пакет с официального сайта https://www.process-one.net/en/ejabberd/downloads/

или:

1) **`sudo apt update`**  - обновляем информацию о репозиториях, 

<i>последняя актуальная вресия для данной OS - Ejabberd 16.01</i>

---
2) **`sudo apt-get install ejabberd`** - устанавливаем с репозитрия Ubuntu - Ejabebrd
---
3) **`sudo apt-get install erlang-p1-mysql`** - важный пакет erlang для работы с DB Mysql
---
4) **`sudo service ejabberd stop`** - останавливаем сервис для дальнейшей конфигурации
---


