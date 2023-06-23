# Docker

## Установка Docker:
Убедитесь, что Docker уже установлен на вашей системе Linux Manjaro. Если нет, выполните следующие команды в терминале:
```sh
sudo pacman -Syu
sudo pacman -S docker
```

## Запуск контейнера:

Создайте файл с расширением .Dockerfile (например, Dockerfile) и определите базовый образ и инструкции для сборки контейнера. Пример простого Dockerfile для Python:
```sh
Dockerfile
FROM python:3.9
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "app.py"]
```

В терминале перейдите в каталог, содержащий Dockerfile, и выполните следующую команду для сборки контейнера:
```sh
docker build -t <image_name> .
```

Замените <image_name> на имя вашего образа.

После успешной сборки контейнера вы можете запустить его с помощью команды:
```sh
docker run <image_name>
```

## Работа с контейнером:

Подключение к работающему контейнеру:
```sh
docker exec -it <container_id> bash
```
Замените <container_id> на идентификатор вашего контейнера.

Остановка контейнера:
```sh
docker stop <container_id>
```
Замените <container_id> на идентификатор вашего контейнера.

Удаление контейнера:
```sh
docker rm <container_id>
```
Замените <container_id> на идентификатор вашего контейнера.

Просмотр списка работающих контейнеров:
```sh
docker ps
```
Просмотр списка всех контейнеров:
```sh
docker ps -a
```


## Работа с образами:

Загрузка образа из Docker Hub:
```sh
docker pull <image_name>
```
Замените <image_name> на имя образа, который вы хотите загрузить.

Просмотр списка локально загруженных образов:
```sh
docker images
```
Удаление образа:
```sh
docker rmi <image_name>
```
Замените <image_name> на имя образа, который вы хотите удалить.
