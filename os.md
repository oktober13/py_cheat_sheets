# import os

## Получить текущую рабочую директорию
current_dir = os.getcwd()

## Сменить текущую рабочую директорию
os.chdir('/path/to/directory')

## Получить список файлов и папок в директории
file_list = os.listdir('/path/to/directory')

## Создать новую папку
os.mkdir('/path/to/new_directory')

## Создать новые папки рекурсивно
os.makedirs('/path/to/new_directory/subdirectory', exist_ok=True)

## Проверить, существует ли файл или папка
file_exists = os.path.exists('/path/to/file_or_directory')

## Проверить, является ли путь файлом
is_file = os.path.isfile('/path/to/file')

## Проверить, является ли путь папкой
is_directory = os.path.isdir('/path/to/directory')

## Получить абсолютный путь к файлу или папке
absolute_path = os.path.abspath('file_or_directory')

## Объединить пути
path = os.path.join('/path/to', 'file_or_directory')

## Разделить путь на базовую часть и имя файла или папки
base_path, file_name = os.path.split('/path/to/file_or_directory')

## Разделить расширение файла от его имени
file_name, file_extension = os.path.splitext('file.ext')

## Удалить файл
os.remove('/path/to/file')

## Переименовать файл или папку
os.rename('/path/to/old_name', '/path/to/new_name')

## Удалить пустую папку
os.rmdir('/path/to/empty_directory')

## Удалить папку и все ее содержимое рекурсивно
os.removedirs('/path/to/directory')

## Получить информацию о файле
file_info = os.stat('/path/to/file')

## Получить размер файла в байтах
file_size = file_info.st_size

## Получить время последней модификации файла в формате timestamp
modification_time = file_info.st_mtime
## Получить имя текущего пользователя
current_user = os.getlogin()

## Создать символическую ссылку
os.symlink('/path/to/target', '/path/to/symlink')

## Получить информацию о файловой системе, на которой расположен путь
file_system_info = os.statvfs('/path/to/directory')


## Получить имя домашней директории текущего пользователя
home_directory = os.path.expanduser('~')

## Выполнить команду в терминале
os.system('command')

## Получить переменные окружения
env_variable = os.environ.get('VAR_NAME')

## Установить переменную окружения
os.environ['VAR_NAME'] = 'value'

## Удалить переменную окружения
del os.environ['VAR_NAME']

## Получить список аргументов командной строки
command_line_args = sys.argv

## Выйти из программы
os.exit()

## Запустить другую программу
os.execvp('program', ['arg1', 'arg2'])

## Изменить права доступа к файлу или папке
os.chmod('/path/to/file', 0o755)

## Получить текущий процессорный идентификатор (PID)
pid = os.getpid()

## Получить идентификатор родительского процесса (PPID)
ppid = os.getppid()

## Получить текущую рабочую группу процесса
process_group = os.getpgrp()
