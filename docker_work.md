# Шпаргалка по Docker

## Основные команды

### 1. Запуск и управление контейнерами
- Запуск контейнера:
  docker run -it <image_name>
  Пример:
  docker run -it ubuntu

- Запуск контейнера в фоновом режиме:
  docker run -d <image_name>

- Запуск существующего остановленного контейнера:
  docker start <container_id_or_name>

- Вход в работающий контейнер:
  docker exec -it <container_id_or_name> /bin/bash

- Остановка контейнера:
  docker stop <container_id_or_name>

- Удаление контейнера (останавливается автоматически):
  docker rm <container_id_or_name>

- Запуск контейнера с указанием порта (например, 8080):
  docker run -p 8080:80 -it <image_name>

### 2. Работа с образами
- Список всех образов:
  docker images

- Загрузка образа из Docker Hub:
  docker pull <image_name>
  Пример:
  docker pull ubuntu

- Создание нового образа из контейнера:
  docker commit <container_id> <new_image_name>

- Удаление образа:
  docker rmi <image_id_or_name>

### 3. Информация о контейнерах и образах
- Список всех контейнеров (включая остановленные):
  docker ps -a

- Список запущенных контейнеров:
  docker ps

- Информация о контейнере:
  docker inspect <container_id_or_name>

- Информация о Docker:
  docker info

### 4. Работа с томами (Volumes)
- Список всех томов:
  docker volume ls

- Создание нового тома:
  docker volume create <volume_name>

- Запуск контейнера с монтированием тома:
  docker run -v <host_path>:<container_path> -it <image_name>

- Удаление тома:
  docker volume rm <volume_name>

### 5. Сетевые настройки
- Создание новой сети:
  docker network create <network_name>

- Подключение контейнера к сети:
  docker network connect <network_name> <container_id_or_name>

- Просмотр информации о сетях:
  docker network ls

- Удаление сети:
  docker network rm <network_name>

### 6. Логи контейнера
- Просмотр логов контейнера:
  docker logs <container_id_or_name>

- Просмотр логов контейнера в реальном времени:
  docker logs -f <container_id_or_name>

### 7. Удаление контейнеров и образов
- Удаление всех остановленных контейнеров:
  docker container prune

- Удаление всех неиспользуемых образов:
  docker image prune

- Удаление всех контейнеров и образов:
  docker system prune -a

### 8. Дополнительные полезные команды
- Запуск контейнера с ограничением ресурсов (например, памяти):
  docker run -m 512m -it <image_name>

- Остановка контейнера и его удаление:
  docker rm -f <container_id_or_name>

- Запуск контейнера с переменными окружения:
  docker run -e <ENV_VAR_NAME>=<value> -it <image_name>

- Просмотр информации о ресурсе (CPU, память):
  docker stats

### 9. Docker Compose (если используется)
- Запуск всех сервисов из docker-compose.yml:
  docker-compose up

- Запуск сервисов в фоне:
  docker-compose up -d

- Остановка всех контейнеров, запущенных через Docker Compose:
  docker-compose down

- Просмотр логов всех сервисов:
  docker-compose logs

