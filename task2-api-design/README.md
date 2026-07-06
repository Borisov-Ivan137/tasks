# Задание 2: проектирование API

# Описание:
Интернет-магазин "Петрушка Зеленая" преуспевает, расширяется и в мобильном
приложении решили создать новый экран, который будет отображать магазины
партнеров (см. макеты ниже).

# Что нужно сделать:
1. Написать пример REST API запроса, который будет вызываться при переходе
пользователя на данный экран.
2. Привести пример ответа этого REST API в соответствии с макетом. Формат -
JSON. Учесть, что при клике на плашку магазина должен осуществляться
переход по ссылке на внешний ресурс

## Запрос (Request)

**Метод:** `GET`  
**Эндпоинт:** `/api/v1/stores`  
**Заголовки:**
- `Authorization: Bearer <access_token>` (опционально)
- `Accept: application/json`

**Параметры запроса (query string):**
- `lat` (число, опционально) – широта пользователя
- `lng` (число, опционально) – долгота
- `city` (строка, опционально) – город (если геолокация недоступна)

**Пример полного URL:**
GET /api/v1/stores?lat=55.7558&lng=37.6173
---

## Ответ (Response)

**Успешный ответ (200 OK):**

```json
{
  "status": "success",
  "data": {
    "stores": [
      {
        "id": "metro_001",
        "name": "METRO",
        "deliveryInfo": "Ближайшая доставка сегодня 21:00-23:00",
        "link": "https://www.metro-cc.ru/"
      },
      {
        "id": "ashan_002",
        "name": "Ашан",
        "deliveryInfo": "Ближайшая доставка сегодня 18:00-20:00",
        "link": "https://www.auchan.ru/"
      },
      {
        "id": "vkusvill_003",
        "name": "ВкусВилл",
        "deliveryInfo": "Быстрая доставка от 20 до 60 минут",
        "link": "https://vkusvill.ru/"
      },
      {
        "id": "victoria_004",
        "name": "ВИКТОРИЯ",
        "deliveryInfo": "Ближайшая доставка сегодня 17:00-19:00",
        "link": "https://victoria-group.ru/"
      },
      {
        "id": "victoria_005",
        "name": "ВИКТОРИЯ",
        "deliveryInfo": "Ближайшая доставка сегодня 17:30-19:30",
        "link": "https://victoria-group.ru/"
      }
    ]
  }
}

Ошибка (пример):

{
  "status": "error",
  "message": "Не удалось загрузить список магазинов"
}

Сохраните файл.

---

#### 📄 Файл `response-example.json` (чистый JSON)

Создайте новый файл в корне репозитория с именем `response-example.json` и вставьте туда только JSON-объект (без пояснений):

```json
{
  "status": "success",
  "data": {
    "stores": [
      {
        "id": "metro_001",
        "name": "METRO",
        "deliveryInfo": "Ближайшая доставка сегодня 21:00-23:00",
        "link": "https://www.metro-cc.ru/"
      },
      {
        "id": "ashan_002",
        "name": "Ашан",
        "deliveryInfo": "Ближайшая доставка сегодня 18:00-20:00",
        "link": "https://www.auchan.ru/"
      },
      {
        "id": "vkusvill_003",
        "name": "ВкусВилл",
        "deliveryInfo": "Быстрая доставка от 20 до 60 минут",
        "link": "https://vkusvill.ru/"
      },
      {
        "id": "victoria_004",
        "name": "ВИКТОРИЯ",
        "deliveryInfo": "Ближайшая доставка сегодня 17:00-19:00",
        "link": "https://victoria-group.ru/"
      },
      {
        "id": "victoria_005",
        "name": "ВИКТОРИЯ",
        "deliveryInfo": "Ближайшая доставка сегодня 17:30-19:30",
        "link": "https://victoria-group.ru/"
      }
    ]
  }
}
