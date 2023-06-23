# ORM

ORM (Object-Relational Mapping) в Python - это подход, который позволяет работать с базой данных, используя объектно-ориентированный стиль программирования. Вместо написания прямых SQL-запросов, вы работаете с объектами и классами, которые соответствуют таблицам и записям в базе данных.

ORM берет на себя задачи по преобразованию объектов Python в структуры данных базы данных и обратно, что позволяет вам более удобно работать с данными.
Вот пример:

Предположим, у вас есть таблица "users" в базе данных, которая содержит столбцы "id", "name" и "email". С ORM вы можете создать класс User, который будет соответствовать этой таблице:

from sqlalchemy import Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base

Base = declarative_base()

class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    name = Column(String)
    email = Column(String)

В этом примере класс User наследуется от declarative_base(), предоставляемого SQLAlchemy. Атрибуты класса User (например, id, name, email) соответствуют столбцам таблицы.

Теперь вы можете использовать этот класс для работы с данными базы данных без необходимости писать SQL-запросы напрямую. Например, вы можете создать нового пользователя и сохранить его в базе данных:

from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

engine = create_engine("database://username:password@hostname/database_name")

Session = sessionmaker(bind=engine)
session = Session()

user = User(name='John', email='john@example.com')
session.add(user)
session.commit()

ORM позволяет вам также выполнять запросы к базе данных, обновлять и удалять объекты с помощью простых методов, а также автоматически обрабатывать множество задач, связанных с базой данных.
