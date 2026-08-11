# Системи тест-менеджменту та управління проєктами (Завдання №6)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW06_Test_Management_Systems_Hurtova.pdf)
> Проєкт CatPaw Share у TestRail: [Переглянути Test Run](https://qahelvetas7.testrail.io/index.php?/runs/view/18&group_by=cases:section_id&group_order=asc&display=tree)
> Проєкт Prom.ua у TestRail: [Переглянути Test Run](https://qahelvetas7.testrail.io/index.php?/runs/view/19&group_by=cases:section_id&group_order=asc&display=tree)

---

## English Summary

Project Overview:  
This repository contains Homework #6 for the Software Testing and QA course. The assignment focuses on deploying test infrastructure in TestRail for two independent products, executing test cycles with real metrics, and conducting a comparative analysis of 5 project management and test management systems for a startup team of 10.

Key Scope & Topics Covered:

TMS Theory & Architecture: Argumentation for TMS adoption over Excel — separation of test template from execution process, Traceability, Time Management via Burndown Charts, and Forecasting metrics. Key TMS qualities identified: test base isolation, atomicity, visual analytics, and bug-tracker integration.

Practical Test Execution in TestRail: Migration of 10 test cases from Excel into TestRail across two isolated projects — CatPaw Share (mobile cat photo-sharing startup, 80% Passed / 20% Failed) and Prom.ua Marketplace (authorization & search testing, 70% Passed / 30% Failed with 3 defects: Viber timer violation, RESULT_CODE_HUNG browser error, irrelevant search results by article code).

Comparative Analysis of 5 Systems: Cost-benefit evaluation of Jira, TestRail, Azure DevOps, Trello, and Asana for a 10-person team — including hidden costs (Azure DevOps Test Plans at $52/user/month). Final recommendation: Jira (free for ≤10 users) + TestRail ($370/month) integration for optimal quality control and budget.

---

## Основні результати та практичні рішення

### 1 Теорія систем тест-менеджменту (TMS Theory)
Обґрунтовано ключову перевагу TMS над Excel: відокремлення шаблону інструкції від процесу її виконання з можливістю коригування під безліч конфігурацій. Визначено чотири критичні особливості TMS для забезпечення якості:
Цілісність та ізоляція бази тестів: Розбиття за Sections та проектами для паралельної роботи команди.
Атомарність та однозначність: Кожен крок містить чітку дію та конкретний очікуваний результат.
Наочна аналітика: Автоматичні кругові діаграми (Passed / Failed / Untested) для відображення готовності до релізу.
Інтеграція з баг-трекерами: Наскрізний зв'язок TestRail ↔ Jira для миттєвої передачі деталей дефектів.

---

### 2 Практика виконання тестів у TestRail (Test Execution)
Перенесено та структуровано тест-кейси у два незалежні проекти TestRail:

**CatPaw Share — Anna** (MVP Full Regression Run, Build v1.0.0): 80% Passed, 20% Failed. Позитивні сценарії реєстрації успішні; сценарій завантаження >10 МБ — FAILED через симуляцію дефекту валідації.

**Prom.ua Marketplace — Anna** (Authorization & Search Testing, v1.0): 70% Passed, 30% Failed. Зафіксовано 3 дефекти: порушення таймера Viber OTP, зависання з помилкою `RESULT_CODE_HUNG`, нерелевантна видача за артикулом товару.

---

### 3 Порівняльний аналіз систем для стартапу (5 Tools Comparison)
Проведено аналіз п'яти систем (Jira, TestRail, Azure DevOps, Trello, Asana) з точною калькуляцією вартості для команди з 10 осіб:

| Система | Вартість / міс. |
|---------|----------------|
| Jira (Free) | $0 |
| TestRail Professional | $370 |
| Azure DevOps + Test Plans | $550 |
| Trello (Free) | $0 |
| Asana Starter | $109.90 |

**Фінальне рішення:** Зв'язка **Jira ($0) + TestRail ($370)** — оптимальний баланс між повноцінним QA-інструментарієм та бюджетом стартапу. Trello та Asana відхилено через відсутність концепції тестування.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка теоретичної частини (Блок 1):
> *"Ти дала глибоку і термінологічно точну відповідь: фраза «TMS відокремлює шаблон інструкції від процесу її виконання» точно описує ключову архітектурну відмінність систем тест-менеджменту від Excel, а згадка про Traceability й Time Management прямо перегукується з матеріалами уроку. Особливо вдало розкрито Tier 2 — принцип «Атомарність та однозначність: кожен крок має містити чітку дію та конкретний очікуваний результат» — і ти сама послідовно застосувала цей принцип у своїх тест-кейсах нижче, що показує реальне розуміння. Це вичерпна відповідь, тут нічого додавати не потрібно."*

### Оцінка порівняльного аналізу (Блок 3):
> *"Порівняльний аналіз п'яти систем (Jira, TestRail, Azure DevOps, Trello, Asana) — дуже сильна робота: ти не просто порівняла функціонал, а прорахувала точну вартість для команди з 10 осіб (наприклад, «Azure DevOps... $550 / місяць» з урахуванням додаткового модуля Test Plans), що демонструє розуміння прихованих витрат, які легко упустити. Фінальний висновок — обрати зв'язку Jira ($0) + TestRail (платно) — логічно обґрунтований і прямо відповідає на запитання завдання, пояснюючи, чому Trello та Asana не підходять («фізично не вміють фіксувати покрокові перевірки, оцінки часу та конфігурації середовищ»). Це вичерпний і по-справжньому прикладний аналіз."*  
> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Розгортання тестової інфраструктури: Практичний досвід створення проєктів, секцій та тестових циклів у TestRail з ізоляцією баз тестів між різними продуктами.

Виконання тестів та фіксація метрик: Мануальне проходження Test Runs із виставленням статусів Passed/Failed та аналізом результатів — включно із симуляцією реальних дефектів (валідація файлів, помилки авторизації, нерелевантний пошук).

Бізнес-аналіз інструментів: Порівняльна оцінка 5 систем з калькуляцією прихованих витрат (модуль Test Plans в Azure DevOps) та обґрунтуванням оптимальної зв'язки для стартапу.

Розуміння архітектури TMS: Чітке усвідомлення відмінності між шаблоном тесту та його виконанням, ролі Traceability, Forecasting та Burndown Charts у контролі якості.
