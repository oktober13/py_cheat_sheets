# re
```
import re
```
## Поиск совпадений
```
pattern = r"apple"
text = "I have an apple"
match = re.search(pattern, text)
if match:
    print("Найдено совпадение!")
else:
    print("Совпадение не найдено.")
```
## Поиск всех совпадений
```
matches = re.findall(pattern, text)
print(matches)
```
## Замена совпадений
```
new_text = re.sub(pattern, "orange", text)
print(new_text)
```
## Использование групп
```
pattern2 = r"(\d{2})-(\d{2})-(\d{4})"
date = "Today is 21-05-2023"
match2 = re.search(pattern2, date)
if match2:
    day = match2.group(1)
    month = match2.group(2)
    year = match2.group(3)
    print(f"День: {day}, Месяц: {month}, Год: {year}")
```
## Разделение строки
```
text2 = "apple,banana,cherry"
items = re.split(",", text2)
print(items)
```
## Поиск слова в начале строки
```
pattern = r"^Hello"
text = "Hello, World!"
match = re.search(pattern, text)
if match:
    print("Совпадение найдено в начале строки!")
```
## Поиск слова в конце строки
```
pattern2 = r"World$"
match2 = re.search(pattern2, text)
if match2:
    print("Совпадение найдено в конце строки!")
```
## Игнорирование регистра
```
pattern3 = r"apple"
text2 = "I have an Apple"
match3 = re.search(pattern3, text2, re.IGNORECASE)
if match3:
    print("Совпадение найдено, игнорируя регистр!")
```
## Извлечение всех чисел из строки
```
pattern4 = r"\d+"
text3 = "I have 3 apples and 5 bananas"
numbers = re.findall(pattern4, text3)
print(numbers)
```
## Проверка соответствия шаблону
```
pattern5 = r"^\w+$"
words = ["hello", "123", "Hello123", "123World"]
for word in words:
    if re.match(pattern5, word):
        print(f"Слово '{word}' соответствует шаблону.")
    else:
        print(f"Слово '{word}' не соответствует шаблону.")
```
