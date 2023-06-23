# import sqlite3

## Установка соединения с базой данных
conn = sqlite3.connect('database.db')

## Создание курсора для выполнения SQL-запросов
cursor = conn.cursor()

## Создание таблицы
create_table_query = '''
CREATE TABLE IF NOT EXISTS employees (
    id INTEGER PRIMARY KEY,
    name TEXT,
    age INTEGER,
    position TEXT
)
'''
cursor.execute(create_table_query)

## Вставка данных в таблицу
insert_query = '''
INSERT INTO employees (name, age, position)
VALUES (?, ?, ?)
'''
data = ('John Doe', 30, 'Manager')
cursor.execute(insert_query, data)

## Выполнение SELECT-запроса
select_query = 'SELECT * FROM employees'
cursor.execute(select_query)
rows = cursor.fetchall()

for row in rows:
    print(row)

## Обновление данных
update_query = 'UPDATE employees SET position = ? WHERE id = ?'
data = ('Supervisor', 1)
cursor.execute(update_query, data)

## Удаление данных
delete_query = 'DELETE FROM employees WHERE id = ?'
data = (1,)
cursor.execute(delete_query, data)

## Подтверждение изменений и закрытие соединения
conn.commit()
conn.close()
## Выполнение SELECT-запроса с условием
select_query = 'SELECT * FROM employees WHERE age > ?'
data = (25,)
cursor.execute(select_query, data)
rows = cursor.fetchall()
for row in rows:
    print(row)
## Выполнение JOIN-запроса
join_query = '''
SELECT employees.name, departments.department_name
FROM employees
JOIN departments ON employees.department_id = departments.id
'''
cursor.execute(join_query)
rows = cursor.fetchall()

for row in rows:
    print(row)
## Выполнение запроса с использованием параметров из списка
parameters = [30, 'Manager']
parameterized_query = '''
SELECT * FROM employees
WHERE age = ? AND position = ?
'''
cursor.execute(parameterized_query, parameters)
rows = cursor.fetchall()

for row in rows:
    print(row)

## Выполнение запроса с использованием LIKE-оператора
like_query = "SELECT * FROM employees WHERE name LIKE 'J%'"
cursor.execute(like_query)
rows = cursor.fetchall()

for row in rows:
    print(row)

## Закрытие соединения с базой данных
conn.close()
