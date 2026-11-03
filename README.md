# Excel Factory — Google Sheets Report Generator

Автоматический генератор отчётов о продажах на Python с графическим интерфейсом Tkinter и интеграцией с Google Sheets API.

Приложение создаёт тестовые данные о продажах, рассчитывает основные показатели и выгружает готовый отчёт в Google Таблицы с автоматическим форматированием.

## Возможности

- Генерация случайных данных о продажах.
- Выбор количества записей от 5 до 100.
- Отображение данных в графическом интерфейсе.
- Расчёт количества продаж, проданных товаров и общей выручки.
- Интеграция с Google Sheets API.
- Автоматическая выгрузка отчётов в Google Таблицы.
- Очистка предыдущего отчёта перед новой выгрузкой.
- Автоматическое оформление таблицы:
  - объединение ячеек заголовка;
  - цветовое оформление заголовков;
  - форматирование денежных значений;
  - выравнивание данных;
  - границы таблицы;
  - выделение итоговой строки;
  - закрепление строк заголовка;
  - автоматическая настройка ширины столбцов.

## Технологии

- Python 3.12
- Tkinter / ttk
- Google Sheets API v4
- Google Authentication
- Google API Python Client
- python-dotenv

## Структура проекта

```text
google-sheets-report-generator/
├── app/
│   ├── __init__.py
│   ├── google_sheets.py
│   ├── report_data.py
│   └── report_generator.py
├── .env
├── .env.example
├── .gitignore
├── credentials.json
├── requirements.txt
├── README.md
├── main.py
└── test_connection.py
```

Файлы `.env` и `credentials.json` являются локальными конфигурационными файлами и не должны публиковаться в GitHub.

## Установка и запуск

### 1. Клонирование проекта

```bash
git clone https://github.com/USERNAME/google-sheets-report-generator.git
cd google-sheets-report-generator
```

### 2. Создание виртуального окружения

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Установка зависимостей

```bash
python -m pip install -r requirements.txt
```

### 4. Настройка Google Cloud

Для работы приложения необходимо:

1. Создать проект в Google Cloud Console.
2. Включить Google Sheets API.
3. Создать Service Account.
4. Скачать JSON-ключ сервисного аккаунта.
5. Сохранить ключ в корне проекта под именем `credentials.json`.
6. Создать Google Spreadsheet.
7. Предоставить сервисному аккаунту права Editor на эту таблицу.

### 5. Настройка переменных окружения

Создать файл `.env` в корне проекта:

```dotenv
GOOGLE_CREDENTIALS_FILE=credentials.json
GOOGLE_SPREADSHEET_ID=your_sp