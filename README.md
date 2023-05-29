# «Работа с данными (DDL/DML)»
# Александр Широбоков

## Задание 1
 - Поднимаю чистый инстанс MySQL версии 8.25
 - Создаю учётную запись sys_temp.
 - Выполняю запрос на получение списка пользователей в базе данных:

![Снимок экрана (209)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/fc406697-8fea-4ae3-b698-4f4e71aa0cc1)

 - Дайю все права для пользователя sys_temp.
 - Выполняю запрос на получение списка прав для пользователя sys_temp:

![Снимок экрана (210)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/8a0245c5-ae21-42fb-9ac4-d3443444687b)

 - Переподключаюсь к базе данных от имени sys_temp.

 - *Для смены типа аутентификации с sha2 использую запрос: **ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';***

 - По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачиваю дамп базы данных.
 - Восстанавливаю дамп в базу данных.
 - Работаю в командной строке, использую команду для получения всех таблиц базы данных:

![Снимок экрана (211)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/fdffe64c-0ea2-4d86-ab49-453df3adb330)

 - Содержание таблицы actor:

![Снимок экрана (212)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/76241f35-362f-4473-ad57-1718fc5b9d9c)

 - Содержание таблицы film:

![Снимок экрана (213)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/6996a211-62d0-4aff-8ef1-738afd1ffb68)

 - Также с хостовой машины через DBeaver подключаюсь к MySql на виртуальной машине и смотрю получившуюся диаграмму базы sakila:

![Снимок экрана (217)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/56db5baa-8bcd-4907-ad24-388da0c4e872)

## Задание 2
*Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)*

 - Создаю в VisualCode:

![Снимок экрана (219)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/0fde1005-adc8-44e0-8475-b5d2c0c8d4ce)

 - Текстовый вариант:
```
+----------------------------+---------------------------+
| Название таблицы           | Название первичного ключа |
+----------------------------+---------------------------+
| actor                      | actor_id                  |
| actor_info                 | actor_id                  |
| address                    | address_id                |
| category                   | category_id               |
| city                       | city_id                   |
| country                    | country_id                |
| customer                   | customer_id               |
| customer_list              | -                         |
| film                       | film_id                   |
| film_actor                 | (actor_id, film_id)       |
| film_category              | (film_id, category_id)    |
| film_list                  | -                         |
| film_text                  | film_id                   |
| inventory                  | inventory_id              |
| language                   | language_id               |
| nicer_but_slower_film_list | -                         |
| payment                    | payment_id                |
| rental                     | rental_id                 |
| sales_by_film_category     | category                  |
| sales_by_store             | store                     |
| staff                      | staff_id                  |
| staff_list                 | -                         |
| store                      | store_id                  |
+----------------------------+---------------------------+
```


## Задание 3*
 - Убираю у пользователя sys_temp права на внесение, изменение и удаление данных из базы sakila, затем выполняю запрос на получение списка прав для пользователя sys_temp:
![Снимок экрана (215)](https://github.com/AleksandrShirobokov/12.02-DDL-DML-/assets/69298696/097ed657-524d-4fb0-9363-cfb6a6266ef0)

