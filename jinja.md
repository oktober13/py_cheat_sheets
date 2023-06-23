# Jinja
```
{% comment %} Комментарий {% endcomment %}

{% if condition %}
    Условный блок
{% elif condition %}
    Второй условный блок
{% else %}
    Иначе
{% endif %}

{% for item in list %}
    Цикл for
{% endfor %}

{% block block_name %}
    Блок контента
{% endblock %}

{% extends "base.html" %}
{% include "partial.html" %}

{{ variable }}  ## Вывод переменной
{{ variable.attribute }}  ## Вывод атрибута переменной
{{ dictionary.key }}  ## Вывод значения словаря по ключу
{{ list[index] }}  ## Вывод элемента списка по индексу
{{ function() }}  ## Вызов функции и вывод результата

{% url 'url_name' %}  ## Генерация URL по имени маршрута
{% static 'path/to/static/file' %}  ## Генерация URL для статического файла

{% csrf_token %}  ## Генерация CSRF-токена
{% trans 'text' %}  ## Перевод текста
{% blocktrans %}text{% endblocktrans %}  ## Блочный перевод текста

{% filter filter_name %}  ## Фильтрация содержимого
    Фильтр
{% endfilter %}

{% with variable=value %}  ## Определение временной переменной
    С переменной
{% endwith %}

{% spaceless %}  ## Удаление пробелов
    Удаление пробелов
{% endspaceless %}

{% if variable is defined %}  ## Проверка на определенность
    Проверка на определенность
{% endif %}

{% if variable is none %}  ## Проверка на None
    Проверка на None
{% endif %}

{% if variable is divisibleby 2 %}  ## Проверка на деление на 2
    Проверка на деление на 2
{% endif %}

{% if variable is divisibleby 3 %}  ## Проверка на деление на 3
    Проверка на деление на 3
{% endif %}

{% if variable is iterable %}  ## Проверка на итерируемость
    Проверка на итерируемость
{% endif %}

{% if variable is sameas other_variable %}  ## Проверка на идентичность
    Проверка на идентичность
{% endif %}
{% macro macro_name(arg1, arg2) %}  ## Определение макроса с аргументами
    Макрос
{% endmacro %}

{% call macro_name(value1, value2) %}  ## Вызов макроса с аргументами
{% endcall %}

{% set variable = value %}  ## Определение переменной
{% set variable %}value{% endset %}  ## Определение переменной с блоком содержимого

{% include "template.html" with variable=value %}  ## Включение другого шаблона с передачей переменных
```
