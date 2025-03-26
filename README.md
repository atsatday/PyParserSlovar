# Парсер словарей с slovaronline.com

## 📖 Обзор

Проект состоит из двух основных скриптов:

1. `parsSlovar.py` - Парсер списка словарей с сайта
2. `dictionary_parser.py` - Основной парсер содержимого словарей

## 🛠 Возможности

- Получение полного списка доступных словарей
- Парсинг содержимого каждого словаря
- Сохранение результатов в структурированном виде
- Поддержка API для получения дополнительной информации

## ⚙️ Установка

### Требования
- Python 3.8+
- Установка зависимостей:
  ```bash
  pip install requests beautifulsoup4
  ```

## parsSlovar.py

### 📝 Описание

Скрипт для получения списка всех доступных словарей с сайта slovaronline.com.

### 🔹 Как использовать

1. Запустите скрипт:
   ```bash
   python parsSlovar.py
   ```

2. Скрипт создаст файл `dictionaries.json` с информацией о всех словарях:

Пример структуры выходного файла:
```json
[
  {
    "title": "Английские частицы",
    "url": "https://english-particles.slovaronline.com",
    "categories": ["Англо-русские"],
    "author": "Иванов И.И.",
    "word_count": "245"
  }
]
```

### 🔹 Особенности

- Автоматическое определение структуры страницы
- Обработка всех доступных словарей
- Случайные задержки между запросами для избежания блокировки
- Сохранение полной информации о каждом словаре

### 🔹 Функции

- `get_dictionaries()`: Основная функция парсинга списка словарей
- `save_to_json()`: Сохранение результатов в JSON-файл

## dictionary_parser.py

### 📝 Описание

Основной скрипт для парсинга содержимого словарей из полученного списка.

### 🔹 Как использовать

1. Убедитесь, что есть файл `dictionaries.json`
2. Запустите скрипт:
   ```bash
   python dictionary_parser.py
   ```
3. При запросе введите API-ключ (если доступен)

### 🔹 Особенности

- Создает папку `BaseSlovar` с результатами
- Для каждого словаря создает отдельную подпапку
- Сохраняет слова в различных форматах
- Поддерживает обработку через API

### 🔹 Выходные данные

Для каждого словаря создается структура:
```
BaseSlovar/
└── Название_словаря/
    ├── all_words.txt
    ├── words/
    │   ├── word_1.txt
    │   └── ...
    ├── phrases/ (при использовании API)
    │   ├── phrases_1.json
    │   └── ...
    └── descriptions/ (при использовании API)
        ├── descriptions_1.txt
        └── ...
```

## ⚠️ Важные замечания

1. Используйте случайные задержки между запросами
2. API-ключ требуется для получения расширенной информации
3. Скрипты могут потребовать адаптации под изменения структуры сайта

## 📜 Лицензия

Проект распространяется под лицензией MIT.
