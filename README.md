# Домашнее задание к занятию «Работа с данными (DDL/DML)»
### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp. 

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

1.4. Дайте все права для пользователя sys_temp. 

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*

---

- Установка mysql:
![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql1.jpg)

- Проверка статуса и версии mysql:
![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql2.jpg)

- Запуск mysql от имени пользователя root
- Создание учетной записи sys_temp
- Выполнение запроса на получение списка пользователей в базе данных:
![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql3.jpg)

- Выполнение запроса на получение списка прав для пользователя sys_temp:
![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql4.jpg)

- Таблицы базы данных в терминале:
![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql5.jpg)

- Таблицы базы данных в DBeaver:
![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql6.jpg)

### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы | Название первичного ключа
customer         | customer_id
```
---

![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql7.jpg)

![install](https://github.com/OhotinDY/sdb-12-02/blob/main/sql8.jpg)

Конфигурационный файл: 

```
nano /etc/mysql/mysql.conf.d/mysqld.cnf
```

```
# Copyright (c) 2014, 2023, Oracle and/or its affiliates.
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License, version 2.0,
# as published by the Free Software Foundation.
#
# This program is also distributed with certain software (including
# but not limited to OpenSSL) that is licensed under separate terms,
# as designated in a particular file or component or in included license
# documentation.  The authors of MySQL hereby grant you an additional
# permission to link the program and your derivative works with the
# separately licensed software that they have included with MySQL.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License, version 2.0, for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301  USA

#
# The MySQL  Server configuration file.
#
# For explanations see
# http://dev.mysql.com/doc/mysql/en/server-system-variables.html

[mysqld]
pid-file	= /var/run/mysqld/mysqld.pid
socket		= /var/run/mysqld/mysqld.sock
datadir		= /var/lib/mysql
log-error	= /var/log/mysql/error.log

bind-address	= 0.0.0.0
server-id	= 1
log_bin		= /var/log/mysql/mysql-bin.log
```
