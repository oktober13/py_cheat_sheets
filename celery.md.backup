# Celery

```
from celery import Celery

# Создание экземпляра Celery
app = Celery('myapp', broker='amqp://guest@localhost//')

# Определение задачи
@app.task
def add(x, y):
    return x + y

# Отправка задачи в очередь
result = add.delay(4, 5)

# Получение результата
print(result.get())
```

## Настройка Celery

```
from celery import Celery

# Создание экземпляра Celery с указанием конфигурации
app = Celery('myapp', broker='amqp://guest@localhost//', backend='rpc://')

# Дополнительная конфигурация
app.conf.task_default_queue = 'my-queue'
app.conf.task_default_exchange = 'my-exchange'
app.conf.task_default_routing_key = 'my-routing-key'
```

## Запуск Celery

```
celery -A myapp worker --loglevel=info
```

## Отправка задачи в очередь

```
from myapp import add

# Отправка задачи в очередь
result = add.delay(4, 5)

# Получение результата
print(result.get())
```

## Получение результатов выполнения задачи

```
result = add.delay(4, 5)

# Проверка статуса выполнения задачи
print(result.ready())

# Получение результата (если задача выполнена)
print(result.get())
```
