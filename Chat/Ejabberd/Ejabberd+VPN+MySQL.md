<h2>Установка и настройка подключения Ejabberd 16.01 по VPN к удаленным серверам, с централизованным хранением сообщений и личных карт пользователей в БД Mysql</h2>


1) <h3>Установка на ОС Ubuntu 16.04:</h3>

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

2) <h3>Установка и настройка БД Mysql</h3>

Устанавливаем пакет с репозитория Ubuntu:

---
1) **`sudo apt-get install mysql`**
---
2) **`sudo service mysql start`**
---

Логинимся в Mysql и создаем новую БД с именем Ejabberd:
---
3) **`mysql -u root -p`**
4) **`CREATE DATABASE ejabberd;`**
---
Создаем нового пользователя с именем ejabberd и закрываем Mysql:

5) **`GRANT ALL ON ejabberd.* TO 'ejabberd'@'localhost' IDENTIFIED BY 'пароль пользователя';`**
6) **`quit;`**

3) <h3>Конфигурация сервера<h3>

После установки пакета, проверяем наличие файла ejabberd.yml командой list по пути:


