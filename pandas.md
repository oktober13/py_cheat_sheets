# Pandas

import pandas as pd

## Создание DataFrame из списка словарей
data = [
    {'Name': 'John', 'Age': 30, 'City': 'New York'},
    {'Name': 'Alice', 'Age': 25, 'City': 'London'},
    {'Name': 'Bob', 'Age': 35, 'City': 'Paris'}
]
df = pd.DataFrame(data)

## Вывод первых нескольких строк DataFrame
print(df.head())

## Отбор данных по условию
filtered_df = df[df['Age'] > 30]
print(filtered_df)

## Группировка данных и вычисление агрегатных функций
grouped_df = df.groupby('City').mean()
print(grouped_df)

## Сортировка данных по столбцу
sorted_df = df.sort_values('Age', ascending=False)
print(sorted_df)

## Запись DataFrame в файл CSV
df.to_csv('data.csv', index=False)

## Чтение данных из файла CSV в DataFrame
new_df = pd.read_csv('data.csv')

## Изменение типа данных столбца
new_df['Age'] = new_df['Age'].astype(float)
print(new_df.dtypes)

## Выбор отдельных столбцов
name_column = df['Name']
print(name_column)

## Добавление нового столбца
df['Salary'] = [5000, 6000, 4000]
print(df)

## Удаление столбца
df = df.drop('Salary', axis=1)
print(df)

## Применение функции к каждому элементу столбца
df['Age'] = df['Age'].apply(lambda x: x + 1)
print(df)

## Объединение DataFrame по ключу
data1 = {'Name': ['John', 'Alice'], 'Age': [30, 25]}
data2 = {'Name': ['Bob'], 'Age': [35]}
df1 = pd.DataFrame(data1)
df2 = pd.DataFrame(data2)
merged_df = pd.concat([df1, df2])
print(merged_df)

## Объединение DataFrame по индексу
df3 = pd.DataFrame({'Salary': [5000, 6000]}, index=[0, 1])
merged_df2 = pd.concat([df1, df3], axis=1)
print(merged_df2)

## Объединение DataFrame по ключу или индексу
df4 = pd.DataFrame({'City': ['New York', 'London', 'Paris']})
merged_df3 = pd.merge(df1, df4, left_index=True, right_index=True)
print(merged_df3)

## Объединение DataFrame по ключу или индексу с помощью SQL-подобного синтаксиса
merged_df4 = pd.merge(df1, df4, on='City')
print(merged_df4)

## Применение агрегатных функций к группам данных
grouped_df2 = df.groupby('City').agg({'Age': 'mean', 'Salary': 'sum'})
print(grouped_df2)
## Сортировка DataFrame по столбцу
sorted_df = df.sort_values(by='Age')
print(sorted_df)

## Запись DataFrame в CSV-файл
df.to_csv('data.csv', index=False)

## Чтение данных из CSV-файла
new_df = pd.read_csv('data.csv')
print(new_df)

## Запись DataFrame в Excel-файл
df.to_excel('data.xlsx', index=False, sheet_name='Sheet1')

## Чтение данных из Excel-файла
new_df = pd.read_excel('data.xlsx', sheet_name='Sheet1')
print(new_df)

## Переименование столбцов
df = df.rename(columns={'Age': 'Years'})
print(df)

## Преобразование столбца в тип данных datetime
df['Date'] = pd.to_datetime(df['Date'])
print(df.dtypes)

## Заполнение пропущенных значений
df = df.fillna(0)
print(df)

## Удаление строк с пропущенными значениями
df = df.dropna()
print(df)
