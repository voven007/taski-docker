# Описание

Taski – сервис для создания онлайн заметок. Проект реализован на фреймворке Django.

Использован Django REST Framework для создания REST API. Проект подготовлен к развертыванию на сервере с использованием Docker контейнеров и оркестрации Docker Compose. Реализован процесс CI/CD с помощью GitHub Actions (активация происходит при push в ветку releases). При успешном деплое на сервер происходит отправка сообщения в Telegram.

# Автор проекта

[Vladimir](https://github.com/voven007)

# Установка и запуск с Docker

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/voven007/taski-docker
```

```
cd taski-docker
```

Запустить сборку проекта:

```
docker compose up
```

Выполнить сбор статики в контейнере backend:

```
docker compose exec backend python manage.py collectstatic
```

Выполнить миграции в контейнере backend:

```
docker compose exec backend python manage.py migrate
```

Проект будет доступен по адресу

```
http://127.0.0.1:8000/
```

# Спецификация

При локальном запуске документация будет доступна по адресу:

```
http://127.0.0.1:8000/redoc/ или http://127.0.0.1:8000/swagger/
```

# Примеры запросов к API

### Получение списка заметок

Описание метода: Получить список заметок. Права доступа: Аутентифицированные пользователи.

Тип запроса: `GET`

Эндпоинт: `/api/tasks/`

Пример успешного ответа:

```
[
  {
    "id": 0,
    "title": "string",
    "description": "string",
    "completed": true
  }
]
```

### Добавление новой заметки

Описание метода: Добавление новой заметки. Права доступа: Аутентифицированные пользователи.

Тип запроса: `POST`

Эндпоинт: `/api/tasks/`

Пример запроса:

```
{
  "title": "string",
  "description": "string",
  "completed": true
}
```

Пример успешного ответа:

```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "completed": true
}
```
