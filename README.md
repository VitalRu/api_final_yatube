## Описание:

Проект YaTube-API. Это социальная сеть, где пользователи могут публиковать свои
посты, размещать их в группах, комментировать свои посты и посты других
пользователей, а также подписываться на других авторов.

![Static Badge](https://img.shields.io/badge/python-3.9.10-blue?style=for-the-badge&logo=python&labelColor=yellow) ![Static Badge](https://img.shields.io/badge/django-%25?style=for-the-badge&logo=django) ![Static Badge](https://img.shields.io/badge/REST_API-%25?style=for-the-badge&color=279EFF)


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

## Примеры запросов

### Регистрация нового пользователя

POST-запрос
```
http://127.0.0.1:8000/api/v1/users/
```
```
{
    "username": "user_one",
    "password": "veRy5tr0nGpASSw0rd"
}
```

### Получение JWT-токена

POST-запрос
```
http://127.0.0.1:8000/api/v1/jwt/create/
```

### Создание публикации.

POST-запрос:


```
http://127.0.0.1:8000/api/v1/posts/
```

Тело запроса
```
{
    "text": "some post text"
}
```

Ответ
```

{
    "id": 1,
    "author": "user_one",
    "text": "some post text",
    "pub_date": "2023-05-15T12:15:03.615183Z",
    "image": null,
    "group": null
}
```
### Получение списка всех постов

GET-запрос
```
http://127.0.0.1:8000/api/v1/posts/
```

пример ответа
```
[
    {
        "id": 1,
        "author": "user_one",
        "text": "some post text",
        "pub_date": "2023-05-15T12:15:03.615183Z",
        "image": null,
        "group": null
    }
]
```