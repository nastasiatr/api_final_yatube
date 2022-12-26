# ЯП - Спринт 9 - Проект «API для Yatube». Python-разработчик (бекенд) (Яндекс.Практикум)

### Технологии
Python 3.7, Django 3.2, DRF, JWT + Djoser
### Запуск проекта в dev-режиме
- Клонировать репозиторий и перейти в него в командной строке.
- Установите и активируйте виртуальное окружение c учетом версии Python 3.7 (выбираем python не ниже 3.7):
```bash
py -m venv venv
source venv/Scripts/activate
python -m pip install --upgrade pip
```
- Устанаввливаем зависимости из файла requirements.txt
```bash
pip install -r requirements.txt
```
- Выполняем миграции:
```bash
python manage.py migrate
```
Создаем суперпользователя:
```bash
python manage.py createsuperuser
```
Запускаем проект:
```bash
python manage.py runserver
```
