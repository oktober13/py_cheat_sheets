# Docker
    1. Установка Docker:
        ◦ Убедитесь, что Docker уже установлен на вашей системе Linux Manjaro. Если нет, выполните следующие команды в терминале:
    • sudo pacman -Syu
      sudo pacman -S docker


      2. Запуск контейнера:
      
    • Создайте файл с расширением .Dockerfile (например, Dockerfile) и определите базовый образ и инструкции для сборки контейнера. Пример простого Dockerfile для Python:
      Dockerfile
FROM python:3.9
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "app.py"]
    • В терминале перейдите в каталог, содержащий Dockerfile, и выполните следующую команду для сборки контейнера:
    • docker build -t <image_name> .
Замените <image_name> на имя вашего образа.
    • После успешной сборки контейнера вы можете запустить его с помощью команды:
    • docker run <image_name>


      3. Работа с контейнером:
      
    • Подключение к работающему контейнеру:
    • docker exec -it <container_id> bash
Замените <container_id> на идентификатор вашего контейнера.
    • Остановка контейнера:
    • docker stop <container_id>
Замените <container_id> на идентификатор вашего контейнера.
    • Удаление контейнера:
    • docker rm <container_id>
Замените <container_id> на идентификатор вашего контейнера.
    • Просмотр списка работающих контейнеров:
    • docker ps
    • Просмотр списка всех контейнеров:
    • docker ps -a


      4. Работа с образами:
      
    • Загрузка образа из Docker Hub:
    • docker pull <image_name>
Замените <image_name> на имя образа, который вы хотите загрузить.
    • Просмотр списка локально загруженных образов:
    • docker images
    • Удаление образа:
docker rmi <image_name>
Замените <image_name> на имя образа, который вы хотите удалить.
