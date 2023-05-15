# Финальная версия проекта YaMDB, API-версия.

![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)

![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/Straga33/api_final_yatube)
![GitHub repo size](https://img.shields.io/github/repo-size/Straga33/api_final_yatube)
![GitHub](https://img.shields.io/github/license/Straga33/api_final_yatube)
![pythonversion](https://img.shields.io/badge/python-%3E%3D3.7-blue)

## Описание:

Финальная версия проекта YaMDB, API-версия. Применены все знания теоретической части по теме django-rest-framework. Это социальная сеть для публикации своих постов. Поддерживает разные тематические группы. Авторство и подписки.  

## Стек технологий:

* Python 3.8
* Django framework 2.2.16
* Django REST Framewor 3.12.4
* PyJWT 2.1.0
* Pillow 8.3.1
* Requests 2.26.0

## Установка:

Перейти в каталог с проектом

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source env/bin/activate
```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

## Примеры:

полный список примеров API: 
```
http://127.0.0.1:8000/redoc/
```

### Получить список всех публикаций. 

При указании параметров limit и offset выдача работаtn с пагинацией.

запрос:

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

