# Лабораторно-практична робота №3
Цей проєкт реалізує **REST API**.  
API підтримує аутентифікацію та авторизацію за ролями, а також демонструє роботу з основними HTTP-методами.  

## Встановлення та запуск
```
npm install
```
```
npm start
```
```
npm test
```
## Приклади роботи API (Postman)
✅ Успішні запити
### 200
![](/img/200.1.jpg)
![](/img/200.2.jpg)
![](/img/200.3.jpg)
![](/img/200.4.jpg)
![](/img/200.5.jpg)
![](/img/200.6.jpg)
![](/img/200.7.jpg)
### 201
![](/img/201.1.jpg)
![](/img/201.2.jpg)

❌ Помилка 400

![](/img/400.jpg)

❌ Помилка 401 (Unauthorized)

![](/img/401.1.jpg)
![](/img/401.2.jpg)
![](/img/401.3.jpg)

❌ Помилка 403 (Forbidden)
![](/img/403.1.jpg)
![](/img/403.2.jpg)

❌ Помилка 404 (Not Found)
![](/img/404.jpg)

## Таблиця ендпоінтів

| Метод  | URL                | Опис                              | Заголовки (Auth)                          | Тіло запиту (JSON)                                  | Коди відповіді |
|--------|--------------------|-----------------------------------|-------------------------------------------|-----------------------------------------------------|----------------|
| GET    | `/documents`       | Отримати список всіх документів   | `X-Login`, `X-Password`                   | –                                                   | 200 OK, 401 Unauthorized |
| POST   | `/documents`       | Створити новий документ           | `X-Login`, `X-Password`                   | `{ "title": "Q3 Report", "content": "..." }`        | 201 Created, 400 Bad Request, 401 Unauthorized |
| DELETE | `/documents/:id`   | Видалити документ за ID           | `X-Login`, `X-Password`                   | –                                                   | 204 No Content, 401 Unauthorized, 404 Not Found |
| GET    | `/employees`       | Отримати список співробітників    | `X-Login`, `X-Password` (роль `admin`)    | –                                                   | 200 OK, 401 Unauthorized, 403 Forbidden |
| GET    | `/non-existent`    | Звернення до неіснуючого ресурсу | `X-Login`, `X-Password` (опціонально)     | –                                                   | 404 Not Found |

## Посилання на репозиторій
🔗 [secure-api-lab (GitHub)](https://github.com/DenysKryvosheiev/secure-api-lab)
