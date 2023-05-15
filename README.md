## Описание:

Проект YaTube-API. Это социальная сеть, где пользователи могут публиковать свои
посты, размещать их в группах, комментировать свои посты и посты других
пользователей, а также подписываться на других авторов.

## Установка:

Находясь в каталоге проекта, создать и активировать виртуальное окружение:


для Linux
```
python3 -m venv venv

source env/bin/activate
```

для Windows
```
python -m venv venv

source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:
```
pip install -r requirements.txt
```

Выполнить миграции:
```
python manage.py makemigrations
python manage.py migrate
```

Запустить проект:
```
python manage.py runserver
```

Документация проекта: 
```
http://127.0.0.1:8000/redoc/
```

### Примеры запросов

```
GET http://127.0.0.1:8000/api/v1/posts/?limit=2
```

ответ:
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```

### Обновление публикации. 

Обновление публикации по id. Обновить публикацию может только автор публикации. Анонимные запросы запрещены.

запрос:

```
PUT http://127.0.0.1:8000/api/v1/posts/{id}/

{
"text": "string",
"image": "string",
"group": 0
}
```

### Удаление комментария.

Удаление комментария к публикации по id. Обновить комментарий может только автор комментария. Анонимные запросы запрещены.

запрос:

```
DELETE http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/
```

### Получить JWT-токен.

Получение JWT-токена.

запрос:

```
POST http://127.0.0.1:8000/api/v1/jwt/create/

{
"username": "string",
"password": "string"
}
```

### Разработчик:

Басков Михаил (baem-festa@yandex.ru)

