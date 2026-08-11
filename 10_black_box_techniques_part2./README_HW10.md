# Домашня робота: Практика техніки тест-дизайну Black Box. Частина 2 (Завдання №10)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW10_Black_Box_Techniques_Part2_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #10 for the Software Testing and QA course. The assignment covers practical application of Black Box test design techniques: State Transition Testing, Decision Table Testing, and Use Case specification — applied to TV remote control systems, employee bonus logic, a video game quest ("Castle of Riddles"), and the CatPaw Share mobile application.

Key Scope & Topics Covered:

TV State Transition Diagram (3 States, 5 Transitions): Complete state diagram for S1 (TV Off), S2 (TV StandBy), S3 (TV Play) with 5 valid transitions (Power ON, Power Off ×2, RC On, RC Off). Correct identification that the test case set covers 100% of all valid transitions per ISTQB State Transition Testing standards.

Employee Bonus Decision Table: Analysis of a 3-condition decision table (tenure > 1 year, goals assigned, goals achieved) to identify the missing realistic scenario — D: employee works < 1 year (Condition 1 = NO), has assigned goals (Condition 2 = YES), fails to meet them (Condition 3 = NO), resulting in no bonus (Action = NO). Valid combinatorial case for negative testing.

Castle of Riddles Video Game (State Transition Diagram + 7 Test Cases): Full state transition diagram with 6 states (Castle room, Witch riddle, Dragon riddle, 2nd Dragon riddle, Exit/Win, Game Over/Lose) and branching logic. Enumeration of all 7 test paths achieving 100% coverage of valid transitions: 5 winning paths and 2 losing paths through combinations of left/right corridor choices and correct/incorrect answers.

CatPaw Share — Use Cases, State Diagram & Decision Table: 5 formal Use Cases (UC-01 through UC-05) covering photo publication (Happy Path), invalid file size upload (Exception Path), invalid format upload (Exception Path), comment writing (Happy Path), and post deletion (Happy Path). State transition diagram with 4 states (Post Creation Screen, Validation Error, Published, Deleted) and 4 transitions. Decision Table for UC-01 with 2 conditions (file size 10KB–10MB, format .jpg/.png/.svg/.webp) generating 2² = 4 test variants with clear pass/fail outcomes.

---

## Основні результати та практичні рішення

### 1 Діаграма переходу станів телевізора (State Transition Testing)
Побудовано діаграму з 3 станами (TV Off, TV StandBy, TV Play) та 5 валідними переходами. Правильно визначено, що тестовий набір забезпечує 100% покриття всіх валідних переходів за стандартами ISTQB.

### 2 Таблиця рішень — бонуси співробітників (Decision Table Testing)
Визначено пропущений реалістичний сценарій (Умова 1 = НІ, Умова 2 = ТАК, Умова 3 = НІ, Дія = НІ) — співробітник на випробувальному терміні з поставленими, але не виконаними цілями. Валідний комбінаторний кейс для негативного тестування.

### 3 Відеогра «Замок загадок» (State Transition Diagram + Path Testing)
Складено діаграму станів та переходів з 6 станами та розгалуженою логікою двох персонажів (дракон і відьма). Перелічено всі 7 тест-кейсів (шляхів) для 100% покриття валідних переходів: 5 шляхів до перемоги та 2 шляхи до поразки.

### 4 CatPaw Share — Use Cases, діаграма станів та таблиця рішень
Розроблено 5 варіантів використання (UC-01 — UC-05): 3 Happy Path та 2 Exception Path. Побудовано діаграму переходу станів із 4 станами життєвого циклу поста. Створено таблицю рішень для UC-01 з 2 умовами та 4 тестовими варіантами.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек та внесено виправлення:

### Оцінка задач Must have рівня:
> *"Перше питання розібране на дуже високому рівні — з посиланням на ISTQB та чітким підрахунком: «на діаграмі зафіксовано рівно 5 можливих шляхів... даний набір тестів забезпечує 100% покриття» — відповідь B повністю правильна й аргументована."*

### Виправлення за результатами рецензії:

**Задача 2 (Таблиця рішень — бонуси):** Початкова відповідь A потребувала перегляду — обґрунтування допускало, що працівник міг «показати високі результати» навіть без офіційно поставленої цілі (Умова 2 = НІ, Умова 3 = ТАК). Ментор зазначила, що не можна формально «досягти» цілі, якої не існувало. Виправлено на варіант D (Умова 1 = НІ, Умова 2 = ТАК, Умова 3 = НІ, Дія = НІ) — прямий і послідовний реальний сценарій.

**Задача «Замок загадок» (Діаграма станів):** У початковій діаграмі був пропущений перехід «правильна відповідь на другу загадку Дракона → Вихід з Замку» та зазначено лише 4 тест-кейси без переліку конкретних шляхів. Після зауваження ментора діаграму доповнено відсутнім переходом та складено повний перелік усіх 7 тест-кейсів для 100% покриття.

### Оцінка задач Програма максимум:
> *"Дуже сильна робота: 5 use-кейсів (UC-01–UC-05) чітко розділені на Happy Path та Exception Path, з конкретними технічними деталями (формати .jpg/.png/.svg/.webp, межі розміру файлу) — це саме той рівень деталізації, який робить use-кейси придатними для прямого перетворення в тест-кейси."*

> *"Діаграма станів логічно об'єднує кілька написаних сценаріїв (створення поста → помилка/публікація → видалення), а не обмежується одним ізольованим кейсом."*

> *"Таблиця рішень для UC-01 — окремо хочу відзначити: замість абстрактних Так/Ні ти взяла реальні файли — це наближає таблицю рішень до практичного тест-дизайну і показує зрілий підхід до параметризації тестів."*
> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Тестування переходу станів (State Transition Testing): Побудова діаграм станів і переходів для різних систем (телевізор, відеогра, мобільний додаток) з визначенням необхідної кількості тест-кейсів для повного покриття валідних переходів.

Таблиці рішень (Decision Table Testing): Застосування комбінаторного аналізу умов для виявлення пропущених сценаріїв та побудова таблиць рішень із чітким визначенням очікуваних дій системи для кожної комбінації.

Варіанти використання (Use Case Specification): Написання формальних Use Cases із зазначенням акторів, кроків та очікуваних результатів для Happy Path та Exception Path сценаріїв.

Аналіз покриття шляхів (Path Coverage): Систематичне перелічення всіх можливих шляхів у розгалуженій логіці системи для досягнення 100% покриття переходів.
