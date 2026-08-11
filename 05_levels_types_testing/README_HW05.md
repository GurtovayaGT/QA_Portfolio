# Рівні та типи тестування програмного забезпечення (Завдання №5)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW05_Levels_Types_Testing_Hurtova.pdf)
> Тест-кейси та NFR: [Переглянути таблицю (Google Sheets)](https://docs.google.com/spreadsheets/d/1wae4iivJA5BA3Rx4xwNIK0Xbqma_lMgL/edit?usp=sharing&ouid=100346096209743919858&rtpof=true&sd=true)

---

## English Summary

Project Overview:  
This repository contains Homework #5 for the Software Testing and QA course. The assignment focuses on comparative analysis of testing types (functional, non-functional, change-related), argumentation for comprehensive testing strategies, and practical application of non-functional requirements with test cases for a mobile application.

Key Scope & Topics Covered:

Comparative Analysis of Testing Types: Detailed 4-criterion comparison (what is tested, when conducted, limitations, specifics) across functional, non-functional, and change-related testing — with clear differentiation between Retesting (Confirmation Testing) and Regression Testing explained in 5 structured sentences.

Argumentation Against Functional-Only Testing: Three-risk analysis (financial losses, legal/security risks, development unprofitability) demonstrating why non-functional testing is mandatory, plus justification of Smoke Testing as a critical quality gate before deep verification.

Non-Functional Requirements & Test Cases: Specification of 4 NFRs (Performance, Compatibility, Security, Reliability) for a cat photo-sharing app with measurable criteria and concrete verification methods (DevTools/Network, real test devices, Charles Proxy, invalid format handling). Full positive and negative test cases documented in a separate Google Sheets artifact.

---

## Основні результати та практичні рішення

### 1 Порівняльний аналіз типів тестування (Comparative Analysis)
Побудовано структуровану таблицю порівняння трьох типів тестування за чотирма критеріями:
Функціональне тестування: Перевірка технічної реалізації бізнес-функцій за методом «чорної скриньки» на основі ТЗ. Проводиться з появою першої готової функції. Обмеження — не враховує поведінку під навантаженням.
Нефункціональне тестування: Перевірка характеристик якості (швидкість, надійність, безпека, сумісність). Потребує спеціалізованого ПЗ (JMeter) та чітких цифрових метрик.
Тестування, пов'язане зі змінами: Ділиться на **Ретестінг** (підтвердження виправлення конкретного багу) та **Регресію** (перевірка стабільності всієї системи після змін).

---

### 2 Аргументація проти виключно функціонального тестування
Обґрунтовано три критичні ризики відмови від нефункціонального тестування:
Фінансові втрати: Сервери «впадуть» від навантаження через відсутність перевірки продуктивності.
Юридичні ризики: Витік персональних даних без перевірки шифрування призведе до судових позовів.
Нерентабельність: Повільний або несумісний додаток втрачає користувачів протягом хвилин.

Додатково аргументовано необхідність **димового (Smoke) тестування** як обов'язкового первинного фільтра якості при кожному оновленні програми.

---

### 3 Нефункціональні вимоги та тест-кейси для Cat Photo App
Сформовано 4 нефункціональні вимоги з конкретними інструментами перевірки:
`NFR-01` (Продуктивність): Обробка фото нейромережевим фільтром ≤ 1,5 сек — перевірка через DevTools/Network.
`NFR-02` (Сумісність): Коректне відображення UI на Android 10.0+ та iOS 15.0+ — перевірка на реальних пристроях.
`NFR-03` (Безпека): Шифрування даних за HTTPS — перевірка через Charles Proxy.
`NFR-04` (Надійність): Стабільна робота при завантаженні невалідних форматів (.pdf) — перевірка реакції системи.

Позитивні та негативні тест-кейси задокументовані у [Google Sheets](https://docs.google.com/spreadsheets/d/1wae4iivJA5BA3Rx4xwNIK0Xbqma_lMgL/edit?usp=sharing&ouid=100346096209743919858&rtpof=true&sd=true).

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка тест-кейсів:
> *"Тест-кейси оформлені професійно, з передумовами, тестовими даними, а також окремими колонками «Expected Results» і «Actual Results» — це вже рівень, наближений до реальної тестової документації. Негативний кейс TC_NEG_002 добре перевіряє обмеження продукту: «Система блокує публікацію та виводить повідомлення "На фото не виявлено котика..."» — саме те, що вимагала умова."*

### Оцінка нефункціональних вимог (NFR):
> *"Чотири вимоги (продуктивність, сумісність, безпека, надійність) сформульовані як вимірювані критерії — наприклад, «не довше ніж за 1.5 секунди» або «від версії 10.0» — і для кожної вказано конкретний інструмент перевірки: DevTools/Network, реальні тестові пристрої, Charles Proxy для перехоплення трафіку. Особливо вдалий NFR-04 про обробку невалідного формату файлу (.pdf) — це нетривіальний, практичний кейс на надійність, який мало хто згадує. Це один із найдетальніших наборів NFR серед перевірених робіт."*  
> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Системний порівняльний аналіз: Структурована класифікація типів тестування з чітким розмежуванням функціонального, нефункціонального та change-related тестування — включно з практичним розрізненням ретестінгу та регресії.

Аргументація та критичне мислення: Обґрунтування бізнес-критичності нефункціонального тестування через конкретні сценарії ризиків (фінансові, юридичні, репутаційні).

Формулювання вимірюваних NFR: Кожна нефункціональна вимога містить точні числові критерії та конкретний метод верифікації з використанням професійних інструментів (DevTools, Charles Proxy, реальні пристрої).

Тестова документація: Оформлення тест-кейсів за професійним стандартом із передумовами, тестовими даними та окремими колонками Expected/Actual Results.
