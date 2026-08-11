# Естимація. Практика створення тестової документації (Завдання №11)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW11_Estimation_Test_Documentation_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #11 for the Software Testing and QA course. The assignment covers practical creation of test documentation (high-level and low-level test cases), estimation techniques (WBS, PERT, Triangular Distribution), and test strategy development — applied to the Monobank mobile application (card-to-card transfers) and the CatPaw Share startup project.

Key Scope & Topics Covered:

Monobank Test Case Design (High-Level + Low-Level): One high-level (logical) test case for card transfer verification without specific test data — suitable as a basis for exploratory testing sessions. Three low-level (step-by-step) test cases with precise preconditions, exact card numbers (16-digit), amounts in UAH, and expected UI behaviors: TC-1 (positive — valid 500 UAH transfer), TC-2 (negative — exceeding 1000 UAH balance with 1500 UAH transfer), TC-3 (negative — invalid 10-digit card number instead of required 16 digits).

WBS Decomposition (5 Stages): Full work breakdown structure covering the complete QA engineer cycle: environment preparation, test case authoring, manual test execution, result analysis & Jira/TestRail reporting, and developer communication for defect coordination.

PERT Estimation (142 minutes total): Three-point weighted estimation using the formula E = (O + 4M + P) / 6, applied to all 5 WBS stages. Optimistic, Most Likely, and Pessimistic values provided for each stage with full calculations.

Triangular Distribution (155 minutes total): Simplified three-point estimation using E = (O + M + P) / 3 for comparison. Result is 13 minutes (+9.2%) higher than PERT due to equal weighting of the pessimistic scenario.

Comparative Analysis: PERT provides a more balanced estimate by stabilizing around the most likely time (coefficient 4), making it the preferred tool for first-release project planning. Triangular distribution gives a slightly inflated result but remains useful as an upper-bound reference.

CatPaw Share Test Strategy: Comprehensive test strategy document developed as a separate deliverable for the growing QA team of the CatPaw Share startup.

---

## Основні результати та практичні рішення

### 1 Проектування тест-кейсів для Монобанку
Розроблено 1 високорівневий тест-кейс (гнучкий формат для дослідницького тестування) та 3 низькорівневих тест-кейси з точними тестовими даними: позитивний сценарій переказу 500 грн та два негативних — перевищення балансу (1500 грн) і невалідна довжина номера картки (10 замість 16 цифр).

### 2 Оцінка трудовитрат (WBS + PERT + Triangular)
Декомпоновано процес тестування на 5 етапів WBS. Застосовано дві техніки естимації: PERT (142 хв) та спрощена триточкова (155 хв). Різниця +13 хв (+9.2%) обумовлена рівнозначним врахуванням песимістичного сценарію у спрощеній формулі.

### 3 Тестова стратегія CatPaw Share
Розроблено повноцінний документ тестової стратегії для стартапу, що охоплює організацію тестування в команді, що зростає (оформлений як окремий додаток).

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек та внесено виправлення:

### Оцінка задач Must have рівня:
> *"Це зразковий рівень виконання: високорівневий кейс описаний абстрактно й без конкретних даних, а три низькорівневі кейси чітко з нього випливають і покривають позитивний та два негативні сценарії з точними даними. Особливо цінний доданий розділ «Обґрунтування», де ти сама пояснюєш різницю між high-level і low-level документацією — це показує розуміння концепції, а не просто механічне виконання завдання."*

### Оцінка задач Середнього рівня (WBS + PERT):
> *"Дуже сильний аналітичний підхід: ти порівняла результати, пояснивши, чому PERT стабілізує оцінку навколо M — це рівень, який виходить за межі базових очікувань завдання."*

### Виправлення за результатами рецензії:

**Естимація (мінімальні значення):** Ментор зазначила, що будь-які значення в оцінці менше 30 хвилин не працюють у реальному житті. Початкові O/M-значення на кшталт O=5 хв чи M=10 хв були занадто низькими. Всі три проблемних етапи перераховано з реалістичнішими вхідними даними.

**WBS-декомпозиція (додаткові етапи):** У початковій версії не було окремого етапу на написання самих тест-кейсів та на комунікації з розробниками (узгодження знайдених дефектів). Додано відповідні етапи для повнішої відповідності вимогам завдання — декомпозицію розширено до 5 етапів повного циклу QA.

### Оцінка задач Програма максимум (Тестова стратегія):
> *"Це вичерпний, по-справжньому проєктний документ: Scope із чіткими ролями та строками, Test Approach з рівнями/техніками (Equivalence Partitioning, BVA, Decision Tables), Test Environment зі стратегією відновлення даних, Release Control з entry/exit критеріями та навіть Risk Analysis, де ти прямо посилаєшся на трьохточкову PERT-оцінку з Завдання 2 — це показує вміння пов'язувати різні частини курсу в цілісну картину, а не виконувати завдання ізольовано."*

> *"Матриця затвердження (Product Owner, QA Lead, Lead Developer) і статус «Draft for Review» додають документу реалістичності справжнього корпоративного артефакту."*

**Тестова стратегія (термінологія ISTQB):** За рекомендацією ментора до розділу Test Approach додано явне посилання на два типи стратегій згідно з класичною термінологією ISTQB: Методична стратегія (Methodical Strategy) та Аналітична / Ризик-орієнтована стратегія (Analytical / Risk-based Strategy) — з поясненням, як кожна з них реалізована в документі.

> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Проектування тест-кейсів (Test Case Design): Створення високорівневої та низькорівневої тестової документації для мобільного фінансового застосунку з позитивними та негативними сценаріями.

Декомпозиція робіт (WBS): Розбиття процесу тестування на незалежні логічно завершені етапи, що охоплюють повний цикл роботи QA-інженера.

Естимація (PERT та Triangular): Застосування математичних методів оцінки часу з порівняльним аналізом результатів та обґрунтуванням вибору оптимальної техніки.

Тестова стратегія (Test Strategy): Розробка стратегічного документу для організації тестування в стартапі, що зростає.
