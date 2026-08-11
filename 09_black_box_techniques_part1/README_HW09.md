# Практика техніки тест-дизайну Black Box. Частина 1 (Завдання №9)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW09_Black_Box_Techniques_Part1_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #9 for the Software Testing and QA course. The assignment covers practical application of Black Box test design techniques: Equivalence Class Partitioning (EP), Boundary Value Analysis (BVA), and Pairwise Testing — applied to speed control systems, fitness apps, solar radiation devices, video resolution requirements, and the CatPaw Share mobile application.

Key Scope & Topics Covered:

Speed Control System Analysis (5 Equivalence Zones): Full EP/BVA breakdown across invalid data (< 0 km/h), normal range (0–50), warning zone (51–54), fine zone (56–59), and severe penalty zone (> 60 km/h). Comparison of 2-point vs 3-point BVA methods per ISTQB standards. Correct test data set: 50, 51, 55, 56, 60, 61 covering all boundary pairs. Robustness Testing extension with values 0 km/h and −1 km/h beyond the original specification.

Fitness App EP Coverage: Selection of optimal test data set (666, 999, 2222, 5555, 6666) with critical analysis identifying a gap — the 1000–2000 steps class ("Lежибока") remains uncovered, yet this set provides the best available coverage among all options.

Solar Radiation Device (Combined EP Audit): 7-class coverage audit across 2 parameters (time: 3 classes, intensity: 4 classes). Identification of 3 coverage gaps from existing 3 tests, solved with minimum 2 additional tests via parameter combination (Class B + low, Class B + high).

Video App Discrete Classes: Correct identification that 4 fixed resolutions (640×480, 1280×720, 1600×1200, 1920×1080) form 4 independent equivalence classes requiring 4 test cases. Robustness extension proposed with invalid resolutions (0×0, 100×100, 3840×2160).

CatPaw Share Requirements & Test Design: 7 formal requirements (REQ-PHOTO-001 through REQ-COM-003) covering photo size limits (10 KB – 10 MB), allowed formats (.jpg, .jpeg, .png, .webp), carousel limits (1–10 photos), comment length (1–200 chars), hashtag count (0–5), and anti-spam rate limiting (3 comments per 60 seconds). Full EP/BVA analysis table and 4 Test Case Matrices (TC-CAT-001 through TC-CAT-004) with 27 precise test points: 14 valid BVA boundaries, 4 EP midpoints, 9 invalid Robustness points.

---

## Основні результати та практичні рішення

### 1 Система контролю швидкості (EP + BVA)
Побудовано розширений аналіз із 5 еквівалентними зонами, включаючи невалідний клас (< 0 км/год). Застосовано комбінацію 2-point та 3-point BVA за стандартами ISTQB. Обрано оптимальний набір тестових даних: 50, 51, 55, 56, 60, 61 — три граничні пари для кожного стику класів.

### 2 Фітнес-застосунок (EP-покриття)
Обрано набір 666, 999, 2222, 5555, 6666 як найкраще покриття серед запропонованих варіантів. Самостійно виявлено прогалину: клас 1000–2000 кроків залишається непокритим.

### 3 Пристрій сонячного опромінення (аудит покриття)
Проведено аудит 3 наявних тестів за 7 валідними класами (3 за часом + 4 за інтенсивністю). Виявлено 3 прогалини, закриті 2 додатковими тестами завдяки комбінуванню параметрів.

### 4 Відео-застосунок (дискретні класи)
Визначено, що 4 фіксовані роздільні здатності утворюють 4 окремі класи еквівалентності, що потребують 4 тест-кейси. Запропоновано Robustness-розширення для невалідних роздільностей.

### 5 CatPaw Share — Специфікація вимог та тест-дизайн
Розроблено 7 формальних вимог (REQ-PHOTO-001 — REQ-COM-003). Побудовано EP/BVA-аналіз та 4 матриці тест-кейсів (TC-CAT-001 — TC-CAT-004) із 27 точними тестовими точками: 14 валідних BVA, 4 середні EP, 9 невалідних Robustness.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек:

### Оцінка задач Must have рівня:
> *"Ти правильно обґрунтувала набір «50, 51, 55, 56, 60, 61», чітко розписавши межові пари (50/51, 55/56, 60/61) як стики між класами."*

> *"Відповідь D правильна, і ти самостійно виявила ту саму прогалину, яку варто помітити в цьому завданні: «У даному тестовому наборі відсутній представник для класу від 1000 до 2000 кроків... через що цей клас залишається непокритим». Це саме той рівень критичного аналізу вихідних даних, який очікується від досвідченого тестувальника."*

### Оцінка задач Середнього рівня:
> *"Аудит покриття виконано зразково: ти чітко визначила три прогалини (клас Б за часом, класи «низька» і «висока» за інтенсивністю) і показала, як закрити їх двома тестами за рахунок комбінування параметрів («Клас Б + Клас 2» та «Клас Б + Клас 4»). Правильна відповідь і бездоганна аргументація."*

> *"Ти правильно обрала відповідь із 4 тест-кейсами, пояснивши, що «перелік підтримуваних роздільних здатностей... є переліком окремих, незалежних фіксованих значень», тому кожне утворює власний клас."*  
> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Аналіз класів еквівалентності (EP): Практичне розбиття безперервних числових діапазонів та дискретних переліків на валідні та невалідні класи з вибором оптимальних представників.

Аналіз граничних значень (BVA): Застосування 2-point та 3-point методів за стандартами ISTQB з обґрунтуванням вибору підходу для різних типів меж.

Robustness Testing: Розширення тестового покриття поза межі специфікації для перевірки стійкості системи до екстремальних та невалідних вхідних даних.

Аудит тестового покриття: Вміння аналізувати наявний набір тестів, ідентифікувати прогалини та оптимізувати покриття через комбінування параметрів.

Проектування вимог та тест-дизайн: Повний цикл від написання формальних Requirements до побудови EP/BVA-аналізу та матричних тест-кейсів із 27 точними тестовими точками.
