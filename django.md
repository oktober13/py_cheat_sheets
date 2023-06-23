#  Django Python

## models.py
```sh
from django.db import models

class Post(models.Model):
    title = models.CharField(max_length=100)  ## Поле с заголовком типа CharField
    content = models.TextField()  ## Поле с содержимым типа TextField
    pub_date = models.DateTimeField(auto_now_add=True)  ## Поле с датой публикации типа DateTimeField

    def __str__(self):
        return self.title

```
## views.py
```sh
from django.shortcuts import render
from .models import Post

def post_list(request):
    posts = Post.objects.all()  ## Получаем все объекты модели Post
    return render(request, 'blog/post_list.html', {'posts': posts})
```

## urls.py
```sh
from django.urls import path
from .views import post_list

urlpatterns = [
    path('', post_list, name='post_list'),  ## URL для списка постов
]
```

## post_list.html
```sh
{% for post in posts %}  <!-- Цикл для каждого объекта поста -->
    <h2>{{ post.title }}</h2>  <!-- Вывод заголовка поста -->
    <p>{{ post.content }}</p>  <!-- Вывод содержимого поста -->
    <p>Published on: {{ post.pub_date }}</p>  <!-- Вывод даты публикации поста -->
{% endfor %}
```
Это простой пример использования Django для создания списка постов на веб-странице. Модель Post определяет поля для заголовка, содержимого и даты публикации. В представлении post_list мы получаем все объекты модели Post и передаем их в шаблон post_list.html, где они выводятся с помощью цикла и соответствующих переменных.
