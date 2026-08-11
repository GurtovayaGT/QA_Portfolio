# Домашня робота: Тестування API за допомогою Postman (Завдання №17)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW17_API_Testing_Postman_Hurtova.pdf)
> Postman-колекція: [Homework_17.postman_collection.json](./Homework_17.postman_collection.json)

---

## English Summary

Project Overview:  
This repository contains Homework #17 for the Software Testing and QA course. The assignment covers API testing automation using Postman: designing a structured request collection with variables, pre-request scripts, post-response chaining, positive/negative test scenarios, and Collection Runner execution.

Key Scope & Topics Covered:

Postman Collection Structure (8 Requests, E2E Chain): An automated end-to-end test scenario (Request Chaining) consisting of 8 sequential requests against a REST API (em.staging.api.onereach.ai): 4 positive CRUD operations (POST Create → GET Read → PATCH Edit → DELETE Remove), followed by 4 negative counterparts testing error handling for each method.

Positive Requests with Variables and Chaining: Step 1 — POST Create User: variables {{user_name}} and {{user_city}} injected into Body via Pre-request Script (pm.globals.set), with Post-response script automatically capturing {{user_id}} from server response (pm.globals.set("user_id", pm.response.json().id)) for downstream requests. Step 2 — GET User: {{user_id}} passed as Query parameter (?id={{user_id}}). Step 3 — PATCH Edit User: {{user_id}} passed in Body JSON; PUT was replaced with PATCH after discovering the API returned "No user found" for PUT — a practical API investigation finding. Step 4 — DELETE User: cleanup via ?id={{user_id}}.

Negative Requests (Error Handling): Step 5 — POST with undefined variable {{user_name_negative}} triggers 400 Bad Request with "Validation error: name is invalid". Step 6 — GET with hardcoded invalid ID returns 200 OK but body contains "No users found". Step 7 — PATCH with {{user_id_negative}} in Body returns "No user found". Step 8 — DELETE with {{user_id_negative}} in Params returns "No user found".

Automated Tests (15 Total): Each positive request contains 2 assertions (status code + body/response time validation). Negative requests verify error codes and error message strings. All 15 tests pass in Collection Runner with 0 failures and 0 errors.

---

## Основні результати та практичні рішення

### 1 Колекція Postman (E2E-ланцюжок)
8 запитів (POST, GET, PATCH, DELETE × позитивний/негативний), об'єднаних у наскрізний тестовий сценарій з автоматичною передачею {{user_id}} між кроками через pm.globals.set().

### 2 Автотести та Collection Runner
15 автотестів — перевірки статус-кодів, тіла відповіді та часу відгуку. Запуск через Collection Runner: 15/15 Passed, 0 Failed, 0 Errors.

### 3 Знахідка: PATCH замість PUT
Під час тестування виявлено, що метод PUT повертав «No user found». Запит переведено на PATCH — практичне дослідження особливостей API.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка позитивних запитів:
> *"Базові позитивні запити зроблені грамотно: у POST і PATCH («EDIT user») змінні винесені в тіло — {{user_name}}, {{user_city}}, {{user_id}}, а в GET і DELETE — у параметри запиту через {{user_id}}. Особливо вдале рішення — записувати «name»: «{{user_name}}» і одразу підхоплювати {{user_id}} з відповіді сервера через pm.globals.set(\"user_id\", pm.response.json().id), це дає розуміння того, як Postman працює зі змінними в реальному часі. У кожному з чотирьох позитивних запитів по 2 тести (статус-код + додаткова перевірка тіла або часу відповіді) — вимога виконана повністю."*

### Оцінка негативних сценаріїв:
> *"Ти правильно зрозуміла вимогу цього рівня: замість двох тестів в одному запиті створено окремі позитивні й негативні запити для кожного методу — «Create user (Negative)», «DELETE user (Negative)», «EDIT user (Negative)» тощо."*

### Оцінка ланцюжка змінних та знахідки PUT→PATCH:
> *"Ідея ланцюжка через pm.globals.set(\"user_id\", pm.response.json().id) реалізована грамотно, а знахідка про заміну PUT на PATCH через помилку «No user found» — це саме той рівень практичного дослідження API, який очікується на цьому рівні."*

> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Автоматизація API-тестів у Postman (API Test Automation): Проектування колекції з наскрізними змінними, Pre-request та Post-response скриптами, автоматичним перехопленням даних між запитами (Request Chaining).

Позитивне та негативне тестування API (Positive & Negative Testing): Створення окремих позитивних та негативних сценаріїв для кожного HTTP-методу з перевіркою як успішних відповідей, так і обробки помилок.

Collection Runner (Batch Execution): Запуск повного тестового набору через Collection Runner із збереженням порядку виконання та аналізом метрик (15/15 Passed).

Дослідження API (API Exploration): Самостійне виявлення особливості API (PUT → PATCH) та документування прийнятого рішення з обґрунтуванням.
