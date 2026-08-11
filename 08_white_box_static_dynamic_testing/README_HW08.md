# Статичні та динамічні техніки тестування (Завдання №8)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW08_Static_Dynamic_Testing_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #8 for the Software Testing and QA course. The assignment covers comparative analysis of static vs dynamic testing techniques, White-Box coverage analysis (Statement and Decision Coverage), and algorithm design with full Path Coverage test case specification for the CatPaw Share mobile application.

Key Scope & Topics Covered:

Comparative Analysis of Static vs Dynamic Techniques: Multi-criteria comparison (concept, testing object, timing, methodological basis, specific methods) with detailed listing of Reviews (Technical, Code, Requirements, Design Inspection, Walkthroughs, Formal Inspection), automated static analysis (Linters, Data Flow, Control Flow), and dynamic techniques across Black-Box (Equivalence Class, BVA, Decision Table, State-Transition, Use Case, Pairwise, Domain Analysis), White-Box (Statement, Decision/Branch, Path Testing), Grey-Box (API, DB verification), and Experience-based (Exploratory, Error Guessing) categories. Three advantages and three limitations per technique, each tied to real business consequences.

White-Box Coverage Tasks: Analysis of Decision Coverage for single IF-condition code (correct answer: any test yields 50% coverage since IF has exactly two outcomes). MS Word pseudocode analysis: 1 test for Statement Coverage, 2 tests for Decision Coverage. Statement Coverage minimum: 1 test (Happy Path through TRUE branch).

CatPaw Share Algorithm Design: Structured pseudocode with IF/ELSE/ENDIF operators, SVG flowchart visualization, and minimum test case set of 4 for 100% Path Coverage — covering all branches: groomer address, pet care shop, pet supplies store, and "come back when you have a pet" exit.

---

## Основні результати та практичні рішення

### 1 Порівняльний аналіз статичних та динамічних технік
Побудовано розширену порівняльну таблицю за критеріями: головна концепція, об'єкт тестування, час застосування, методологічна основа та конкретні техніки.

Статичні техніки: Формальні перегляди (Technical Review, Code Review, Requirements Review, Design Inspection, Walkthroughs, Formal Inspection) та автоматизований аналіз (Linter, Data Flow Analysis, Control Flow Analysis).

Динамічні техніки: Black-Box (Equivalence Class, BVA, Decision Table, State-Transition, Use Case, Pairwise, Domain Analysis), White-Box (Statement, Decision/Branch, Path Testing), Grey-Box (API, БД, логи) та Experience-based (Exploratory, Error Guessing).

Сформульовано по 3 переваги та 3 обмеження для кожного підходу з прив'язкою до бізнес-наслідків.

---

### 2 White-Box аналіз покриття (Statement & Decision Coverage)
Розв'язано три практичні задачі з обґрунтуванням:
Задача 1: Одна IF-умова має 2 результати (TRUE/FALSE) — кожен тест покриває 50% рішень.
Задача 2 (MS Word): 1 тест для Statement Coverage (Happy Path), 2 тести для Decision Coverage (TRUE + FALSE гілки).
Задача 3: 1 тест достатній для 100% Statement Coverage лінійного коду.

---

### 3 Алгоритм опитувальника CatPaw Share (Path Coverage)
Структуровано алгоритм із використанням IF/ELSE/ENDIF операторів та побудовано блок-схему (Flowchart).

Визначено мінімальний набір із **4 тест-кейсів** для 100% Path Coverage:
`TC-01`: Має кота → Довгошерста → Потрібен грумер → «Адреса котячої перукарні»
`TC-02`: Має кота → Довгошерста → Не потрібен грумер → «Магазин догляду за шерстю»
`TC-03`: Має кота → Короткошерста → «Магазин зоотоварів»
`TC-04`: Не має кота → «Приходьте пізніше»

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка порівняльного аналізу (Блок 1):
> *"Це найглибший аналіз серед усіх переглянутих робіт — ти не просто порівняла техніки за шаблоном, а додала повноцінну структуру («Об'єкт тестування», «Час застосування», «Методологічна основа», «Використовувані техніки та методи») і перелічила конкретні методи на кшталт «Аналіз потоку даних (Data Flow Analysis)» для статичного та «Equivalence Class, Boundary Value Analysis, Decision Table» для динамічного тестування. Формулювання переваг і обмежень пов'язані з реальними бізнес-наслідками. Підсумок про взаємодоповнюваність обох технік логічно завершує відповідь — тут нічого покращувати не потрібно."*

### Оцінка White-Box задач та алгоритму (Блоки 2–3):
> *"Правильно! Молодчинка! Все правильно! Чудова робота!"*  
> — Nadiia Ovsiannikova (Ментор)

### Враховані рекомендації:
На основі зворотного зв'язку ментора на уроці були скориговані обидві блок-схеми алгоритмів.

---

## Ключові навички, продемонстровані в роботі

Системний порівняльний аналіз: Глибоке розуміння відмінностей між статичними та динамічними техніками з класифікацією конкретних методів (Reviews, Linters, Data/Control Flow для статичних; BVA, Decision Table, Exploratory для динамічних).

White-Box тестування: Практичне розуміння Statement Coverage та Decision Coverage — вміння визначати мінімальну кількість тестів для різних рівнів покриття коду.

Проектування алгоритмів: Структурування бізнес-логіки у псевдокод із операторами IF/ELSE/ENDIF, побудова блок-схем та визначення повного набору тест-кейсів для 100% Path Coverage.

Прив'язка теорії до практики: Кожна перевага та обмеження технік аргументована через конкретні бізнес-наслідки, а не абстрактну теорію.
