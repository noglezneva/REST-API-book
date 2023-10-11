#  GO-API 

Простой веб-сервис, предоставляет API для управления книгами в библиотеке. Использует фреймворк Gin для обработки HTTP-запросов и хранит данные о книгах в памяти.

# Запуск

Запустите сервис с помощью команды go run main.go

После запуска Вы сможете делать запросы к сервису по адресу http://localhost:8080

## Пример использования

Некоторые примеры запросов
- [getBooks](#getBooks)
- [bookById](#bookById)
- [createBook](#createBook)
- [chekoutBook](#chekoutBook)
- [returnBook](#returnBook)


### getBooks <a name="getBooks"></a>


Запрос:
```
GET /books

```
Ответ:
```
[
    {
        "id": "1",
        "title": "Crime and Punishment",
        "author": "Fyodor Dostoevsky",
        "quantity": 2
    },
    {
        "id": "2",
        "title": "The Tale of Tsar Saltan",
        "author": "Alexander Sergeyevich Pushkin",
        "quantity": 3
    },
    {
        "id": "3",
        "title": "Anna Karenina",
        "author": "Leo Tolstoy",
        "quantity": 1
    },
    {
        "id": "4",
        "title": "Hamlet",
        "author": "William Shakespeare",
        "quantity": 2
    }
]
```

### bookById <a name="bookById"></a>

Запрос:
```
GET /books/1

```
Ответ:
```
{
    "id": "2",
    "title": "The Tale of Tsar Saltan",
    "author": "Alexander Sergeyevich Pushkin",
    "quantity": 3
}
```

### createBook <a name="createBook"></a>


Запрос:
```
POST /books
{
    "id": "4",
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "quantity": 2
}
```

### chekoutBook <a name="chekoutBook"></a>

Запрос:
```
PATCH /checkout?id=1

```
Ответ:
```
{
    "id": "1",
    "title": "Crime and Punishment",
    "author": "Fyodor Dostoevsky",
    "quantity": 1
}

```
### returnBook <a name="returnBook"></a>

Запрос:
```
PATCH /return?id=1

```
Ответ:
```
{
    "id": "1",
    "title": "Crime and Punishment",
    "author": "Fyodor Dostoevsky",
    "quantity": 2
}

```
