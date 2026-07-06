# Задание 2: Проектирование API

## Запрос (Request)

**Метод:** `GET`  
**Эндпоинт:** `/api/v1/stores`  
**Заголовки:** 
- `Accept: application/json`

**Параметры:**
- `lat` (число, опционально) – широта
- `lng` (число, опционально) – долгота

**Пример:**
GET /api/v1/stores?lat=55.7558&lng=37.6173


---

## Ответ (Response)

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
      }
      // ... остальные магазины
    ]
  }
}
