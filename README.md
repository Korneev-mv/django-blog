# Django Blog — Sitewomen

Учебный Django-проект: блог с админкой, категориями, тегами, связями между моделями и загрузкой файлов.

## Стек

- Python 3.12
- Django 4.2
- SQLite
- Django Debug Toolbar
- Docker + PostgreSQL (в планах)
- Git

## Функционал

- Модели: Women, Category, TagPost, Husband, UploadFiles
- Связи: ForeignKey (Women → Category), ManyToMany (Women ↔ TagPost), OneToOne (Women ↔ Husband)
- Админка: регистрация моделей, настройка отображения, поиск и фильтры
- Формы: AddPostForm (с валидацией), UploadFileForm (загрузка файлов)
- Представления: FBV и CBV (ListView, DetailView, CreateView)
- Шаблоны: наследование, кастомные теги (show_categories, show_all_tags)
- Пагинация, слаги, сортировка, фильтрация по категориям и тегам
- Debug Toolbar для анализа SQL-запросов


## Запуск

1. Клонировать репозиторий:
```bash
git clone https://github.com/Korneev-mv/django-blog.git
cd django-blog
```

2. Создать виртуальное окружение:
```bash
python -m venv djvenv
source djvenv/bin/activate  (Linux/macOS)
djvenv\Scripts\activate     (Windows)
```

3. Установить зависимости:
```bash
pip install -r requirements.txt
```

4. Применить миграции:
```bash
python manage.py migrate
```

5. Создать суперпользователя (для админки):
```bash
python manage.py createsuperuser
```

6. Запустить сервер:
```bash
python manage.py runserver
```

http://127.0.0.1:8000 — сайт.
http://127.0.0.1:8000/admin — админка.

## Модели

| Модель | Описание |
|--------|----------|
| Women | Основная модель (статьи о женщинах) |
| Category | Категории статей |
| TagPost | Теги |
| Husband | Муж (связь OneToOne) |
| UploadFiles | Загруженные файлы |
