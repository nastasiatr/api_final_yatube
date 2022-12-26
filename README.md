# ЯП - Спринт 9 - Проект «API для Yatube».

### Описание
«API для Yatube» это социальная сеть. 
Вы можете создавать собстсенные посты, подписываться на интересующих вас авторов (или отписываться :) ), комментировать записи, управлять своими постами и комметариями.

### Технологии
Python 3.7, Django 3.2, DRF, JWT + Djoser

### Запуск проекта в dev-режиме
- Клонировать репозиторий и перейти в него в командной строке.
- Установите и активируйте виртуальное окружение c учетом версии Python 3.7 (выбираем python не ниже 3.7):

- Создаем виртуальное окружение
```bash
py -m venv venv
```
- Активируем виртуальное окружение
```bash
source venv/Scripts/activate
```
- Обновляем pip
```bash
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
### Примеры работы с API
_Аутентифицированным пользователям разрешено изменение и удаление своего контента; в остальных случаях доступ предоставляется только для чтения.


_У неаутентифицированных пользователей доступ к API только на чтение. Исключение — эндпоинт /follow/: (доступ к нему должен предоставляется только аутентифицированным пользователям)_

### Примеры работы с API для авторизованных пользователей
*Для неавторизованных пользователей работа с API доступна в режиме чтения,
что-либо изменить или создать не получится._

- Создание публикации.
```bash
POST /api/v1/posts/
```
Пример запроса:
в body
```bash
{
"text": "text",
"image": "string",
"group": 1
}
```
Пример ответа:
```bash
{
  "id": 0,
  "author": "string",
  "text": "text",
  "pub_date": "2022-12-24T14:15:22Z",
  "image": "string",
  "group": 1
}
```

- Добавление комментария
```bash
POST  api/v1/posts/{post_id}/comments/
```
Пример запроса:

в body
```bash
{
  "text": "string"
}
```
Пример ответа:
```bash
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2022-12-24T14:15:22Z",
  "post": 1
}
```
