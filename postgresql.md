# PostgreSQL
```
import psycopg2
```
## Установка соединения с базой данных
```
conn = psycopg2.connect(
    host="localhost",  ## Хост базы данных
    port="5432",  ## Порт базы данных
    database="mydatabase",  ## Имя базы данных
    user="myuser",  ## Имя пользователя
    password="mypassword"  ## Пароль пользователя)
```
## Создание курсора для выполнения запросов
```
cur = conn.cursor()
```
## Создание таблицы
```
create_table_query = '''
    CREATE TABLE IF NOT EXISTS employees (
        id SERIAL PRIMARY KEY,
        name VARCHAR(100),
        age INTEGER,
        department VARCHAR(100))'''
cur.execute(create_table_query)
```
## Вставка данных в таблицу
```
insert_query = '''
    INSERT INTO employees (name, age, department)
    VALUES (%s, %s, %s)
'''
data = ("John Doe", 30, "IT")
cur.execute(insert_query, data)
```
## Получение данных из таблицы
```
select_query = '''
    SELECT * FROM employees
'''
cur.execute(select_query)
rows = cur.fetchall()
```
## Вывод результатов
```
for row in rows:
    print("ID:", row[0])
    print("Name:", row[1])
    print("Age:", row[2])
    print("Department:", row[3])
    print()
```
## Обновление данных в таблице
```
update_query = '''
    UPDATE employees
    SET age = %s
    WHERE id = %s
'''
data = (35, 1)
cur.execute(update_query, data)
```
## Удаление данных из таблицы
```
delete_query = '''
    DELETE FROM employees
    WHERE id = %s
'''
data = (1,)
cur.execute(delete_query, data)
```
## Фиксация изменений и закрытие соединения
```
conn.commit()
cur.close()
conn.close()
```
