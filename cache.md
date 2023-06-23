# Кеширование в Python

## Использование декоратора lru_cache из модуля functools:

`from functools import lru_cache`

`@lru_cache(maxsize=None)`
`def cached_function(arguments):`
    # Логика функции
## Установка максимального размера кеша:

_По умолчанию maxsize=None, что означает неограниченный размер._
_Можно указать конкретное число, например, maxsize=100, чтобы ограничить количество сохраняемых результатов._

## Использование декоратора cached_property из модуля cachetools для кеширования свойств:

`from cachetools import cached_property`
`class MyClass:`
    `@cached_property`
    `def cached_property_name(self):`
        # Логика свойства
        
## Использование кастомного кеша с помощью класса Cache из модуля cachetools:

`from cachetools import Cache`
`cache = Cache(maxsize=100)`
`def cached_function(arguments):`
    `if arguments in cache:`
        `return cache[arguments]`
    `else:`
        `result = calculate_result(arguments)`
        `cache[arguments] = result`
        `return result`
## Очистка кеша:
_Декоратор lru_cache автоматически управляет размером кеша._
_Для кастомного кеша можно использовать методы cache.clear() для полной очистки или cache.pop(key) для удаления конкретного элемента._
## Использование кеширования с файлами:
_Можно использовать модуль joblib для кеширования результатов функции в файлы._

Пример:
      
`from joblib import Memory`

`memory = Memory("cache_directory")`

`@memory.cache`
`def cached_function(arguments):`
    # Логика функции
    
### Обработка исключений:

_При использовании кеша, особенно с внешними ресурсами, может возникнуть необходимость обрабатывать исключения, например, при недоступности кеша или ошибке вычислений._
