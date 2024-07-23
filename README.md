# Документация для парсера видеокарт

## Описание

Этот скрипт предназначен для парсинга информации о видеокартах с сайта Rozetka и сохранения данных в CSV файл. Он использует библиотеку `selenium` для получения HTML страницы, `BeautifulSoup` для парсинга HTML, и `csv` для сохранения данных.

## Требования

- Python 3.x
- Библиотеки: `selenium`, `beautifulsoup4`, `csv`
- WebDriver для браузера Chrome (chromedriver)

## Установка зависимостей

Установите необходимые библиотеки с помощью pip:

```sh
pip install selenium beautifulsoup4
```

Убедитесь, что у вас установлен `chromedriver` и он доступен в PATH.

## Описание функций

### `get_data_by_selenium(url: str) -> str`

Забирает HTML-код страницы по указанному URL с использованием Selenium.

**Параметры:**
- `url` (str): URL страницы, которую нужно загрузить.

**Возвращает:**
- `str`: HTML-код страницы.

### `parse_data(data: str) -> list`

Парсит данные из HTML документа.

**Параметры:**
- `data` (str): HTML-код страницы.

**Возвращает:**
- `list`: Список словарей с данными о видеокартах. Каждый словарь содержит следующие ключи:
  - `title` (str): Название видеокарты.
  - `href` (str): Ссылка на страницу видеокарты.
  - `price` (int): Текущая цена.
  - `old_price` (int): Старая цена.

### `save_to_csv(rows: list) -> None`

Сохраняет данные в CSV файл.

**Параметры:**
- `rows` (list): Список словарей с данными о видеокартах.

**Возвращает:**
- None

### `main() -> None`

Главная функция, которая оркестрирует процесс получения и сохранения данных.

**Параметры:**
- Нет

**Возвращает:**
- None

### `random_sleep(min_seconds=1, max_seconds=10) -> int`

Возвращает случайное значение времени ожидания в секундах.

**Параметры:**
- `min_seconds` (int): Минимальное значение времени ожидания.
- `max_seconds` (int): Максимальное значение времени ожидания.

**Возвращает:**
- `int`: Случайное значение времени ожидания в секундах.

## Пример использования

Для запуска скрипта выполните команду:

```sh
python your_script.py
```

Скрипт соберет данные с сайта Rozetka о видеокартах и сохранит их в файл `videocards.csv`.

## Примечания

- Убедитесь, что у вас установлен `chromedriver` и он находится в PATH.
- Скрипт обрабатывает страницы с видеокартами, используя Selenium для загрузки страниц и BeautifulSoup для парсинга.
- Данные сохраняются в CSV файл с разделителем `;`.

## Лицензия

Этот проект лицензирован под лицензией MIT.