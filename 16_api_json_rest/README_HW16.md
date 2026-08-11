# Домашня робота: Тестування API. JSON. REST (Завдання №16)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW16_API_JSON_REST_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #16 for the Software Testing and QA course. The assignment covers API testing fundamentals: writing professional test cases for a live web application, bug reporting on a real REST API endpoint, and hands-on HTTP method testing using ReqBin with Chrome DevTools verification.

Key Scope & Topics Covered:

Level 1 — Test Cases for automoto.ua (5 Test Cases): Five professionally structured test cases (TC-AM-001 through TC-AM-005) with Priority, Type, Preconditions, Test Data, Steps, Expected Result, and Postconditions fields. TC-AM-001 — Negative test for invalid SMS code authentication, verifying not only the error message but also absence of session token in Cookies and Local Storage via DevTools (Priority: Critical, Type: Functional Negative). TC-AM-002 — Positive test for vehicle filtering by category/brand/model/year (Priority: High). TC-AM-003 — Negative test for "Mileage" field validation against invalid input: negative numbers, letters, special characters (Priority: High). TC-AM-004 — Positive test for authorization modal trigger when adding to Favorites as unauthenticated user (Priority: Medium). TC-AM-005 — Positive test for sorting listings by ascending price (Priority: Medium).

Bug Reports for reqres.in API (3 Reports): Three bugs found on POST /api/register endpoint via ReqBin: BUG-001 — Duplicate registration returns existing user's ID instead of 409 Conflict (server returns 201 Created but assigns existing user's ID, violating identifier uniqueness). BUG-002 — Server returns 200 OK and registers existing email with any arbitrary password instead of rejecting the duplicate (creates authorization token for existing user with fabricated password). BUG-003 — Registration succeeds with a single space character as password (server returns 200 OK and generates token instead of 400 Bad Request).

Level 2 — GoREST API Testing via ReqBin (8 Requests): Full HTTP method testing (GET, POST, PUT, PATCH, DELETE) against GoREST /users endpoint through ReqBin with Chrome DevTools (Network tab) cross-verification. Documented ReqBin proxy behavior (requests route through apius.reqbin.com — Headers show proxy POST, Payload contains actual method/URL/body). Bonus endpoints tested: GET /posts (200 OK), GET /todos (200 OK), GET /users.xml (200 OK, XML format) — the last one connecting XML theory from the lesson with practical API output.

---

## Основні результати та практичні рішення

### 1 Тест-кейси для automoto.ua
5 професійних тест-кейсів (TC-AM-001–005) з полями Priority, Type, Preconditions, Test Data, Steps, Expected Result та Postconditions. Включено негативне тестування авторизації (SMS-код) із перевіркою відсутності сесійного токена через DevTools, валідацію поля «Пробіг» на невалідні символи, фільтрацію, сортування та перевірку модального вікна.

### 2 Баг-репорти API (reqres.in)
3 дефекти на ендпоінті POST /api/register: повернення ID існуючого користувача при повторній реєстрації (BUG-001), реєстрація існуючого email з довільним паролем (BUG-002), прийняття пароля з пробілу (BUG-003).

### 3 Тестування GoREST через ReqBin
8 HTTP-запитів (GET, POST, PUT, PATCH, DELETE) до GoREST з верифікацією через Chrome DevTools (Network → Headers + Payload). Задокументовано проксі-поведінку ReqBin. Бонусні ендпоінти: /posts, /todos, /users.xml (XML-формат).

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка тест-кейсів (Рівень 1):
> *"Твої п'ять тест-кейсів виконані на рівні, який виходить за межі базового шаблону — з полями Priority, Type, Preconditions, Test Data та Postconditions, що робить документацію по-справжньому професійною. Особливо вражає TC-AM-001, де очікуваний результат перевіряє не лише повідомлення про помилку, а й «Сесійний токен авторизації відсутній у Cookies та Local Storage (DevTools → вкладка Application → розділ Storage)» — це рівень тестування, який іде далі UI і перевіряє технічний стан застосунку. Так само вдалий TC-AM-003 з перевіркою валідації поля «Пробіг» на негативні кейси (від'ємні числа, літери, спецсимволи) — показує розуміння важливості негативного тестування. Продовжуй у цьому ж дусі — це саме той рівень деталізації, який очікується від тестувальника, що росте в напрямку middle."*

### Оцінка баг-репортів API (reqres.in):
> *"Три знайдені дефекти на POST /api/register оформлені зразково: чіткий ID, кроки відтворення, Expected Result і Actual Result окремо, а BUG-002 «Сервер повертає статус 200 OK, створює токен авторизації та повертає картку з ID існуючого користувача» — справді цікава й реальна знахідка про те, що ендпоінт не перевіряє унікальність email при реєстрації."*

### Оцінка тестування GoREST (Рівень 2):
> *"Твоє пояснення того, чому в DevTools видно запити до «apius.reqbin.com» замість прямого звернення до GoREST, і що це саме проксі-поведінка ReqBin — дуже точне й нетривіальне спостереження, яке демонструє розуміння того, як інструмент працює «під капотом», а не лише як користуватися інтерфейсом. Бонусом ти протестувала додаткові ендпоінти (/posts, /todos, /users.xml), і саме останній чудово ілюструє тему уроку про XML — гарний зв'язок теорії з практикою."*

> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Написання тест-кейсів (Test Case Design): Створення професійних тест-кейсів із повним набором полів (Priority, Type, Preconditions, Test Data, Steps, Expected/Actual Result, Postconditions), включаючи перевірку технічного стану через DevTools.

Тестування API (API Testing): Практичне тестування REST API через ReqBin із виявленням реальних дефектів на ендпоінті реєстрації (дублювання ID, відсутність валідації email та пароля).

HTTP-методи (HTTP Methods): Практичне застосування GET, POST, PUT, PATCH, DELETE до реального API (GoREST) з верифікацією через Chrome DevTools (Network → Headers + Payload).

Розуміння архітектури інструментів (Tool Architecture): Документування проксі-поведінки ReqBin та розуміння відмінностей між даними у DevTools та інтерфейсі інструмента.
