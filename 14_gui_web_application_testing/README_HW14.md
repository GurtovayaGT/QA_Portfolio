# Тестування інтерфейсу користувача (GUI). Тестування вебзастосунків (Завдання №14)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW14_GUI_Web_Application_Testing_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #14 for the Software Testing and QA course. The assignment covers GUI/UX testing of the Oxford Medical website, cross-browser testing across three independent browser engines, and a DevTools audit of UI elements with font, size, color, and background properties.

Key Scope & Topics Covered:

UI/UX Bug Reports for Oxford Medical (5 Reports): Five bug reports (SCRUM-01 through SCRUM-05) for oxford-med.com.ua: SCRUM-01 — UI Overlap of messenger popup over "Leave Review" button in footer (Severity: Low, Priority: Medium). SCRUM-02 — Inconsistent data and broken vertical alignment on specialist cards with missing address/pricing data and uneven padding (Severity: Minor, Priority: High). SCRUM-03 — Incomplete localization on the EN price page with Ukrainian headings mixed into English interface (Severity: Minor, Priority: High). SCRUM-04 — Broken CSS Grid layout on Sitemap page with DevTools confirmation of problematic grid-column-start/end values (Severity: Minor, Priority: Medium). SCRUM-05 — Global draggable image ghost issue across entire website, missing draggable="false" and user-drag: none (Severity: Trivial, Priority: Low).

Cross-Browser Testing Matrix (3 Engines): All 5 bugs verified across three truly independent browser engines: Google Chrome v149.0 (Blink), Apple Safari v17.4.1 (WebKit), Mozilla Firefox v153.0.1 (Gecko) — with exact version numbers. Result: all 5 defects reproduced in all 3 environments, confirming bugs are engine-independent.

DevTools Audit (4 Elements + SCRUM-30): Font/size/color/background inspection of 4 website elements using Chrome DevTools: phone number dropdown in header (Inter, 15.25/18.24px), chat assistant name in Ringostat widget (Open Sans → Inter after reconnect), "Other Cities" button in modal (Inter, 16px, white on transparent), and "Name" placeholder in appointment form (Arial, 13px). Additionally discovered SCRUM-30: critical Ringostat widget initialization failure — WebSocket connection to wss://chat.ringostat.com failed with cascading TypeError (.push() on undefined), blocking call/chat functionality on first load. Auto-reconnected after 15 minutes.

---

## Основні результати та практичні рішення

### 1 Баг-репорти UI/UX (Oxford Medical)
Зафіксовано 5 дефектів інтерфейсу (SCRUM-01–05): накладання компонентів, порушення консистентності карток спеціалістів, неповна локалізація EN-версії прайс-листа, злам CSS Grid на сторінці Sitemap, глобальне перетягування зображень-привидів.

### 2 Крос-браузерне тестування
Усі 5 багів верифіковано у трьох незалежних браузерних рушіях — Blink (Chrome), WebKit (Safari), Gecko (Firefox) — із зазначенням точних версій. Зведена матриця підтвердила 100% відтворюваність дефектів.

### 3 DevTools-аудит + знахідка SCRUM-30
Знято параметри font-family/font-size/color/background для 4 елементів. Паралельно виявлено критичний збій ініціалізації віджета Ringostat (WebSocket failed + TypeError .push()), який блокував функціонал зв'язку при першому завантаженні.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка крос-браузерного тестування:
> *"Ти протестувала у трьох дійсно незалежних браузерних рушіях — Blink (Chrome), WebKit (Safari), Gecko (Firefox) — із зазначенням точних версій, а не просто трьох варіантів одного двигуна. Зведена матриця (ID / назва / Chrome / Safari / Firefox) — це зразковий формат для презентації кросбраузерних результатів. Це найповніша реалізація цього завдання з усіх, що я перевіряла — жодних зауважень!"*

### Оцінка DevTools-аудиту:
> *"Всі 4 задані елементи зняті через DevTools з конкретними значеннями font-family/size/color/background — базова частина завдання виконана бездоганно. Але справжня цінність — у тому, що ти вийшла за межі завдання: знайшла реальний збій WebSocket connection to 'wss://chat.ringostat.com/...' failed і каскадний TypeError, а потім через 15 хвилин повторно перевірила стан і зафіксувала auto-reconnect."*

> *"Такий рівень дослідницького тестування (exploratory testing) значно перевищує очікування — раджу саме цей кейс оформити окремим повноцінним баг-репортом (з ID, Severity/Priority)."*

> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Баг-репортинг UI/UX (GUI Testing): Систематичне виявлення та документування дефектів інтерфейсу з різними рівнями Severity (Trivial–Minor) та пріоритетами, включаючи проблеми локалізації, верстки та візуальної консистентності.

Крос-браузерне тестування (Cross-Browser Testing): Верифікація дефектів у трьох незалежних браузерних рушіях (Blink, WebKit, Gecko) із побудовою зведеної матриці відтворюваності.

DevTools-аудит (Chrome Developer Tools): Практичне використання вкладок Elements, Styles, Computed, Network, Console для інспекції CSS-властивостей, виявлення помилок JavaScript та аналізу WebSocket-з'єднань.

Дослідницьке тестування (Exploratory Testing): Виявлення незапланованого критичного дефекту (SCRUM-30) під час виконання рутинного DevTools-аудиту з повторним ретестом через 15 хвилин для фіксації auto-reconnect.
