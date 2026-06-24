# Django REST API в Docker

REST API сервер на Django с SQLite базой данных в Docker контейнере.

## Переменные окружения

- SECRET_KEY - секретный ключ Django (по умолчанию: django-insecure-dev-key-change-in-production)
- DEBUG - режим отладки (по умолчанию: True)
- ALLOWED_HOSTS - разрешённые хосты (по умолчанию: *)

## Как собрать image

    docker build -t django-api .

## Как запустить контейнер

    docker run -d -p 8000:8000 --name django-api-container django-api

## Как проверить API

Открой браузер: http://localhost:8000/api/items/

Или используй VS Code REST Client / Postman:

### GET запрос - получить все items:
    GET http://localhost:8000/api/items/

### POST запрос - создать item:
    POST http://localhost:8000/api/items/
    Content-Type: application/json

    {
      "name": "Тестовый item",
      "description": "Описание тестового item"
    }

## Как остановить контейнер

    docker stop django-api-container

## Как удалить контейнер

    docker rm django-api-container
