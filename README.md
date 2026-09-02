# Postman-api-testing

Учебный проект по тестированию API с использованием Postman и Newman

## Что здесь есть

- Коллекция запросов с разделением на GET и POST запросы
- Автоматические тесты (проверка статус-кода и данных в ответе)
- Настроенное окружение (Environment) с переменной "baseUrl"
- Тестовые сценарии для успешных и неуспешных ответов сервера (200, 404)

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

## Технологии

Postman, Newman, JavaScript
