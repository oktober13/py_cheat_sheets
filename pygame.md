# import pygame

## Инициализация Pygame
```
pygame.init()
```
## Создание окна
```
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Моя игра")
```
## Цвета
```
white = (255, 255, 255)
black = (0, 0, 0)
```
## Позиция и размеры объекта
```
x = 100
y = 100
width = 50
height = 50
velocity = 5
```
## Главный цикл игры
```
running = True
while running:
    # Обработка событий
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Управление объектом
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        x -= velocity
    if keys[pygame.K_RIGHT]:
        x += velocity
    if keys[pygame.K_UP]:
        y -= velocity
    if keys[pygame.K_DOWN]:
        y += velocity

    # Отрисовка объекта
    screen.fill(white)
    pygame.draw.rect(screen, black, (x, y, width, height))
    pygame.display.update()
```
## Завершение игры
```
pygame.quit()
```
