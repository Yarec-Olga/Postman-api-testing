# Postman-api-testing

Учебный проект по тестированию API с использованием Postman и Newman

## Что здесь есть

- Коллекция запросов с разделением на GET и POST запросы
- Автоматические тесты (проверка статус-кода и данных в ответе)
- Настроенное окружение (Environment) с переменной "baseUrl"
- Тестовые сценарии для успешных и неуспешных ответов сервера (200, 404)
- Mock Server — созданный вручную фейковый сервер с тремя endpoint'ами

## Файлы

- "My Collection.postman_collection.json" - коллекция запросов
- "Development.postman_environment.json" - окружение с переменной

## Через Postman

- Импортировать оба файла через File → Import
- Выбрать окружение "Development" в правом верхнем углу
- Открыть любой запрос и нажать Send

## Через Newman (Терминал)

Требуется установленный Node.js и Newman (`npm install -g newman`)

newman run "My Collection.postman_collection.json" -e "Development.postman_environment.json"

## Mock Server

Изучен и опробован функционал Mock Server в Postman — создание фейкового API-сервера для тестирования эндпоинтов до готовности реального backend.

**Реализованные endpoint'ы:**

* `GET /health` - проверка работоспособности сервера
* `GET /hello` - тестовый ответ с приветственным сообщением
* `GET /products` - список товаров в формате JSON

**Пример ответа `/products`:**

```json
[
  { "name": "Coat", "price": 200 },
  { "name": "Gloves", "price": 70 },
  { "name": "Shawl", "price": 70 }
]
```

Все запросы протестированы вручную, получен успешный ответ 200 OK для каждого endpoint'а.

## Технологии

Postman, Newman, JavaScript


## CI/CD В проект добавлена автоматическая проверка через GitHub Actions (`.github/workflows/tests.yml`) — тесты запускаются автоматически при каждом push с помощью Newman. Один из тестов (`data - 404 error`) намеренно оставлен неуспешным — он демонстрирует, как выглядит `AssertionError` при несовпадении ожидаемого и фактического статус-кода. Это сделано специально для отработки навыка чтения и анализа отчётов о проваленных тестах. 
