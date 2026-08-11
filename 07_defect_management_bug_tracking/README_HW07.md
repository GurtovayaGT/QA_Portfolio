# Управління дефектами та системи баг-трекінгу (Завдання №7)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW07_Defect_Management_Bug_Tracking_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #7 for the Software Testing and QA course. The assignment focuses on production web application defect analysis using Jira, practical Severity/Priority classification with real-world examples, and architectural design of a Bug Life Cycle workflow for a 10-person startup team.

Key Scope & Topics Covered:

Production Defect Reporting (7 Jira Issues + 8 Backlog + 2 UX Recommendations): Exploratory Testing, Business Logic & Content Testing, and UI/UX & Layout Shift Testing of the Headhunter Hairstyling web application. All 7 primary bug reports (SCRUM-19 through SCRUM-26) documented with full Preconditions, Steps to Reproduce, Actual/Expected Results, Environment, Component, Severity, Priority, and media evidence. Additional 8 defects and 2 UX improvement recommendations documented in a structured backlog for future sprints.

Severity vs Priority Practical Analysis: Two non-trivial combinations — Critical Severity / Low Priority (PDF with outdated staff data; 26-second Facebook widget delay) and Minor Severity / Highest Priority (button style desync on main commercial landing zone; conflicting audience instructions on contact form) — each with business-context justification tied to real defects found during testing.

Bug Life Cycle Architectural Design: 7-stage workflow for CatPaw Share startup (To Do → In Progress → Dev Review → Ready for QA → QA Testing → QA Review → Done/Closed) with Rejected/Duplicate terminal branch and Reopened safety filter. Each stage justified for a 10-person manual testing team with practical explanations (e.g., Ready for QA prevents testing empty builds, QA Review ensures cross-platform verification on both iOS and Android before release).

---

## Основні результати та практичні рішення

### 1 Виявлення та документування дефектів (Jira Bug Reporting)
На базі веб-додатка Headhunter Hairstyling проведено комплексне тестування трьох типів:
Exploratory Testing: Вільне дослідницьке тестування для виявлення неочевидних дефектів.
Business Logic & Content Testing: Аналіз відповідності текстового контенту та бізнес-логіки.
UI/UX & Layout Shift Testing: Перевірка динамічних елементів, анімацій та ефектів (паралакс, каруселі, blur-ефекти).

Задокументовано **7 пріоритетних баг-репортів** у Jira (SCRUM-19 — SCRUM-26) з повним заповненням усіх полів: Preconditions, Steps to Reproduce, Actual/Expected Result, Environment, Component, Severity, Priority та медіа-докази.

Додатково зафіксовано **8 дефектів** у беклозі для майбутніх спринтів та **2 UX-рекомендації** щодо покращення інформаційної архітектури сайту.

---

### 2 Аналіз комбінацій Severity та Priority
Відпрацьовано навички визначення критичності та бізнес-пріоритету на реальних прикладах:

**Critical Severity / Low Priority:** PDF прайс-лист із неактуальними даними стороннього майстра (дезінформація, але мінімальний % завантажень) та затримка 26 сек. у віджеті Facebook (критична, але на сайті-візитці без авторизації).

**Minor Severity / Highest Priority:** Розсинхронізація кнопок на першому екрані (технічно працюють, але знижують конверсію «Call Us» — головної комерційної дії) та конфлікт аудиторій на сторінці Contact (форма працює, але дезорієнтує і клієнтів, і бізнес-партнерів).

---

### 3 Життєвий цикл дефекту для CatPaw Share (Bug Life Cycle)
Спроектовано 7-ступеневий workflow для Jira:

`To Do / New` → `In Progress` → `Dev Review / Fixed` → `Ready for QA` → `QA Testing` → `QA Review` → `Done / Closed`

З двома додатковими гілками:
`Rejected / Duplicate` — термінальна гілка для невалідних або повторних тікетів (додано за рекомендацією ментора).
`Reopened` — захисний фільтр для повернення не повністю виправлених дефектів розробнику.

Ключові архітектурні рішення: етап **Ready for QA** запобігає тестуванню «порожніх» білдів; етап **QA Review** забезпечує крос-платформну перевірку (iPhone + Android) перед релізом.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка баг-репортів (Блок 1):
> *"Це найповніший і найпрофесійніший баг-репортинг серед усіх робіт: сім issue в Jira (SCRUM-19–26) із Preconditions, Steps to Reproduce, Actual/Expected Result, Environment, Component, Severity і Priority — заповнені всі поля, без жодного пропуску. Особливо цінно, що ти не зупинилася на обов'язкових трьох багах, а задокументувала ще 8 додаткових дефектів і 2 UX-рекомендації в окремому беклозі «на майбутні спринти» — це показує розуміння того, що баг-трекінг охоплює не лише «знайдені баги», а й керування пріоритетами роботи команди. Тут нічого покращувати не потрібно — це рівень, до якого варто прагнути іншим студентам."*

### Оцінка життєвого циклу багу (Блок 3):
> *"Твій цикл (To Do/New → In Progress → Dev Review/Fixed → Ready for QA → QA Testing → QA Review → Done/Closed, з гілкою Reopened) — найдетальніший з усіх переглянутих робіт, і обґрунтування кожного етапу прив'язане до конкретної команди з 10 тестувальників, а не до абстрактної теорії: наприклад, пояснення статусу Ready for QA («економить час команди на тестування «порожніх» білдів») показує реальне розуміння того, навіщо потрібен цей проміжний крок. Етап QA Review з крос-платформною перевіркою (iPhone і Android) перед релізом — вдале практичне доповнення, якого не було в лекції, але яке логічно випливає з реальної розробки мобільного застосунку."*  
> — Nadiia Ovsiannikova (Ментор)

### Враховані рекомендації:
На основі фідбеку ментора додано гілку **Rejected / Duplicate** одразу після статусу To Do для закриття прогалини у циклі щодо невалідних або повторних тікетів.

---

## Ключові навички, продемонстровані в роботі

Професійний баг-репортинг: Повне документування дефектів у Jira з усіма обов'язковими полями, медіа-доказами та структурованим беклогом — на рівні, визнаному найвищим серед усіх робіт курсу.

Класифікація Severity vs Priority: Розуміння нетривіальних комбінацій (Critical/Low та Minor/Highest) з обґрунтуванням через конкретний бізнес-контекст, а не абстрактну теорію.

Проектування Bug Workflow: Архітектурне рішення для 7-ступеневого життєвого циклу з урахуванням реалій 10-осібної команди — включно з Code Review, крос-платформним аудитом та захисним фільтром Reopened.

Дослідницьке тестування: Практичний досвід Exploratory Testing, Content Testing та UI/UX Testing на production-сайті з виявленням 17 дефектів різної критичності.
