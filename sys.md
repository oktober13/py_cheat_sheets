# import sys

## Получить версию Python
python_version = sys.version

## Получить информацию о платформе
platform_info = sys.platform

## Получить аргументы командной строки
command_line_args = sys.argv

## Получить путь к исполняемому файлу скрипта
script_path = sys.argv[0]

## Получить список модулей, импортированных из библиотеки sys
imported_modules = sys.modules.keys()

## Завершить выполнение программы
sys.exit()

## Получить текущую кодировку
current_encoding = sys.getdefaultencoding()

## Получить список путей для поиска модулей
module_paths = sys.path

## Очистить кэш импортированных модулей
sys.modules.clear()

## Получить идентификатор текущего процесса
pid = sys.pid

## Получить идентификатор родительского процесса
ppid = os.getppid()

## Получить список атрибутов и методов объекта
object_attributes = dir(object)

## Получить количество ссылок на объект
object_refcount = sys.getrefcount(object)

## Получить размер объекта в памяти
object_size = sys.getsizeof(object)
## Получить информацию о памяти, используемой процессом
memory_info = sys.getsizeof(object)

## Получить информацию о текущем использовании памяти
memory_usage = sys.getsizeof(object)

## Получить список путей для загрузки расширений C
c_extensions_paths = sys.get_paths("c")

## Получить информацию о текущем режиме отладки
debug_mode = sys.gettrace()

## Установить режим отладки
sys.settrace(trace_func)

## Получить информацию о текущем обработчике исключений
current_exception_handler = sys.excepthook

## Установить обработчик исключений
sys.excepthook = exception_handler

## Получить текущий размер стека вызовов
call_stack_size = sys.getrecursionlimit()


## Установить размер стека вызовов
sys.setrecursionlimit(new_limit)

## Получить информацию о текущем максимальном размере открытых файлов
max_open_files = sys.maxsize

## Получить текущее значение максимальной глубины рекурсии
recursion_depth = sys.getrecursionlimit()

## Получить список модулей, у которых загруженный код сохраняется в кэше
modules_with_cached_code = sys.getmodulecache()

## Установить значение, указывающее, должен ли интерпретатор Python генерировать отладочную информацию
sys.dont_write_bytecode = True

## Получить текущую директорию
current_directory = sys.path[0]

## Получить список путей к директориям, где ищутся модули
module_search_paths = sys.path

## Добавить путь к директории, где ищутся модули
sys.path.append(directory_path)

## Удалить путь из списка путей, где ищутся модули
sys.path.remove(directory_path)

