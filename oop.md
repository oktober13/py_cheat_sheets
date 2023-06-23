# ООП
## Определение класса:
class ClassName:
    def __init__(self, parameters):
        ## Конструктор класса
        self.attribute = value
    def method(self, parameters):
        ## Метод класса
        ## Доступ к атрибутам класса: self.attribute
        ## Использование параметров
## Создание объекта:
object_name = ClassName(arguments)
## Наследование:
class ChildClass(ParentClass):
    def __init__(self, parameters):
        super().__init__(parameters)
        ## Дополнительная инициализация
    def child_method(self, parameters):
        ## Дополнительные методы
        ## Доступ к методам родительского класса: super().parent_method()
## Инкапсуляция:
    • Атрибуты и методы, которые начинаются с двойного подчеркивания (__), являются приватными и доступны только внутри класса.
## Полиморфизм:
    • Возможность использования одного и того же имени метода в разных классах.
## Атрибуты класса:
    • Общие для всех объектов класса.
    • Объявляются внутри класса, но вне методов.
    • Доступ к атрибутам класса: ClassName.attribute.
## Специальные методы:
    • Методы, начинающиеся и заканчивающиеся двойными подчеркиваниями, например __init__, __str__.
    • Используются для определенных операций, таких как инициализация, строковое представление и т.д.

## Пример использования ООП в Python:
class Circle:
    def __init__(self, radius):
        self.radius = radius
    def area(self):
        return 3.14 * self.radius * self.radius
## Создание объекта класса Circle
my_circle = Circle(5)
print(my_circle.area())  ## Вывод площади окружности
