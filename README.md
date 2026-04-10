# Lab28 — GamesApi

Выполнил студент группы ИСП-231, Плеско Д.Д.

REST API на ASP.NET Core для управления списком любимых игр.
Поддерживает операции GET, POST, PUT, DELETE с хранением данных в памяти сервера.

## Запуск

cd GamesApi && dotnet run

## Маршруты

| Метод  | Маршрут         | Описание            | Статус    |
|--------|-----------------|---------------------|-----------|
| GET    | /api/games      | Получить все игры   | 200       |
| GET    | /api/games/{id} | Получить игру по id | 200 / 404 |
| POST   | /api/games      | Добавить игру       | 201       |
| PUT    | /api/games/{id} | Обновить игру       | 200 / 404 |
| DELETE | /api/games/{id} | Удалить игру        | 204 / 404 |

## Примеры curl-команд

**Получить все игры:**
``` bash
curl http://localhost:5000/api/games
```

**Получить игру по id:**
``` bash
curl http://localhost:5000/api/games/1
```

**Добавить игру:**
``` bash
curl -X POST http://localhost:5000/api/games \
  -H "Content-Type: application/json" \
  -d "{\"title\": \"Hollow Knight\", \"genre\": \"Metroidvania\", \"releaseYear\": 2017}"
```

**Обновить игру:**
``` bash
curl -X PUT http://localhost:5000/api/games/1 \
  -H "Content-Type: application/json" \
  -d "{\"title\": \"Hollow Knight\", \"genre\": \"Action\", \"releaseYear\": 2017}"
```

**Удалить игру:**
``` bash
curl -X DELETE http://localhost:5000/api/games/1
```