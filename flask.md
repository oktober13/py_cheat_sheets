# Flask

from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')  ## Декоратор для определения маршрута "/"
def index():
    return 'Привет, мир!'

@app.route('/hello/<name>')  ## Декоратор для определения маршрута "/hello/<name>"
def hello(name):
    return f'Привет, {name}!'

@app.route('/form', methods=['GET', 'POST'])  ## Декоратор для определения маршрута "/form"
def form():
    if request.method == 'POST':  ## Если запрос методом POST
        name = request.form['name']  ## Получаем значение поля 'name' из формы
        return f'Привет, {name}! Форма отправлена.'
    return render_template('form.html')  ## Выводим шаблон формы

if __name__ == '__main__':
    app.run(debug=True)

Это пример простого приложения Flask. Маршрут / возвращает строку "Привет, мир!". Маршрут /hello/<name> принимает параметр <name> и возвращает персонализированное приветствие. Маршрут /form обрабатывает GET и POST запросы. При GET запросе выводится HTML-форма, а при POST запросе получаем значение поля 'name' и возвращаем персонализированное приветствие с помощью шаблона form.html.
