# PyQt5
```
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow, QPushButton, QLabel
```
## Создание приложения
```
app = QApplication(sys.argv)
```
## Создание главного окна
```
window = QMainWindow()
window.setWindowTitle("Мое приложение")
window.setGeometry(100, 100, 400, 300)
```
## Создание кнопки
```
button = QPushButton("Нажми меня", window)
button.setGeometry(100, 100, 200, 50)
```
## Создание метки
```
label = QLabel("Привет, мир!", window)
label.setGeometry(100, 200, 200, 50)
```
## Обработчик нажатия кнопки
```
def button_clicked():
    label.setText("Кнопка нажата!")
```
## Подключение обработчика к событию нажатия кнопки
```
button.clicked.connect(button_clicked)
```
## Отображение главного окна
```
window.show()
```
## Запуск приложения
```
sys.exit(app.exec())
```
