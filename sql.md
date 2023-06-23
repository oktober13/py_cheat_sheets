# SQL

## Создание таблицы:
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype
);
## Вставка данных в таблицу:
INSERT INTO table_name (column1, column2, column3) VALUES (value1, value2, value3);

## Обновление данных в таблице:
UPDATE table_name SET column1 = new_value1, column2 = new_value2 WHERE condition;

## Удаление данных из таблицы:
DELETE FROM table_name WHERE condition;

## Выборка данных из таблицы:
SELECT column1, column2 FROM table_name WHERE condition;

## Фильтрация данных с использованием условий:
SELECT column1, column2 FROM table_name WHERE column1 = value1 AND column2 > value2;

## Сортировка результатов:
SELECT column1, column2 FROM table_name ORDER BY column1 ASC, column2 DESC;

## Объединение таблиц:
SELECT column1, column2 FROM table1 JOIN table2 ON table1.column = table2.column;

## Группировка данных и агрегатные функции:
SELECT column1, COUNT(column2) FROM table_name GROUP BY column1;

## Использование подзапросов:
SELECT column1, column2 FROM table_name WHERE column1 IN (SELECT column1 FROM table2);

## Создание индекса:
CREATE INDEX index_name ON table_name (column1, column2);

## Создание представления:
CREATE VIEW view_name AS SELECT column1, column2 FROM table_name WHERE condition;

## Создание хранимых процедур:
CREATE PROCEDURE procedure_name
AS
BEGIN
    -- SQL statements
END;

## Создание триггера:
CREATE TRIGGER trigger_name
BEFORE INSERT ON table_name
FOR EACH ROW
BEGIN
    -- SQL statements
END;

## Создание базы данных:
CREATE DATABASE database_name;
