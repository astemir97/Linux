<h2>Установка и настройка подключения Ejabberd 16.01 по VPN к удаленным серверам, с централизованным хранением сообщений и личных карт пользователей в БД Mysql</h2>


1) <h3>Установка на ОС Ubuntu 16.04:</h3>

Загружаем пакет с официального сайта https://www.process-one.net/en/ejabberd/downloads/

или:

1) **`sudo apt update`**  - обновляем информацию о репозиториях, 

<i>последняя актуальная вресия для данной OS - Ejabberd 16.01</i>

---
2) **`sudo apt-get install ejabberd`** - устанавливаем с репозитрия Ubuntu - Ejabebrd
3) **`sudo apt-get install erlang-p1-mysql`** - важный пакет erlang для работы с DB Mysql
4) **`sudo service ejabberd stop`** - останавливаем сервис для дальнейшей конфигурации
---

2) <h3>Установка и настройка БД Mysql</h3>

Устанавливаем пакет с репозитория Ubuntu:

---
1) **`sudo apt-get install mysql`**
2) **`sudo service mysql start`**
---

Логинимся в Mysql и создаем новую БД с именем Ejabberd:

---
3) **`mysql -u root -p`**
4) **`CREATE DATABASE ejabberd;`**
---

Создаем нового пользователя с именем ejabberd и закрываем Mysql:

---
5) **`GRANT ALL ON ejabberd.* TO 'ejabberd'@'localhost' IDENTIFIED BY 'пароль пользователя';`**
6) **`quit;`**
---

3) <h3>Конфигурация сервера<h3>
  
Далее с помощью текстового редактора открываем файл ejabberd.yml с правами суперпользователя:

---
7) **`vim /etc/ejabberd/ejabberd.yml`**
---

<i>"Внимание! Обращаем внимание на то, что файл с расширением .yml имеет крайне чувствительный синтаксис YAML, не рекомендуется переносить строки, ставить лишние пробелы в отличии от тех, которые уже существуют в самом файле, и не в коем случае не нажимать на клавишу табуляции" (Tab).</i>

Находим строку с перечислением хостов hosts, меняем значение localhost на имя вашего сервера:

---
8) **`hosts: ["имя сервера(полоностью)"]
---

Далее находим закоментированную строку ## MySQL server: и меняем значения на те, которые вы ввели mysql, попутно раскоментирую все строки ниже:

---
9)  **`odbc_type: mysql`**
10) **`odbc_server: "localhost"`**
11) **`odbc_database: "ejabberd"`**
12) **`odbc_username: "ejabberd"`**
13) **`odbc_password: "пароль пользователя"`**
---

Находим последнюю строку admin и меняем хост подключения с localhost на имя сервера:

---
14) **`"admin": "bereg.web.local.net"`**
---

Запускаем сервис ejabberd и делаем рестарт ejabberdctl:

---
15) **`sudo service ejabberd start`**
16) **`ejabberdctl start`**
---

Добавляем нового пользователя admin с помощью утилиты ejabberdctl:

---
17) **`ejabberdctl register admin bereg.web.local.net пароль пользователя`**
18) **`sudo service ejabberd restart`**
19) **`ejabberdctl restart`**

Переходим по url-адресу: https://имя_сервера:5280/admin (SSL - обязательно) и вводим JID созданного администратора (admin@имя_сервера) и созданный пароль
