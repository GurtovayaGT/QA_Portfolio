# Домашня робота: Основи тестування мобільних додатків (Завдання №15)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW15_Mobile_Application_Testing_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #15 for the Software Testing and QA course. The assignment covers mobile application testing fundamentals: bug reporting on a real iPhone device, mobile testing checklist development, Android emulator testing via Android Studio, and formal test matrix creation for the national "Diia" (Дія) government application.

Key Scope & Topics Covered:

Level 1 — Real Device Bug Reports (iPhone 16 Pro, Safari, iOS 18): Five bug reports for dpcozt.com.ua (Kyiv City Veterinary Medicine Hospital): BUG-01 — Cropped legal disclaimer about old-format passports on service preview card, classified as Critical (Legal Risk) since truncated text hides cross-border travel restrictions for pet owners. BUG-02 — Cyclical SEO interlinking in blog articles creating infinite redirect loops through synonymized page duplicates (Critical). BUG-03 — Contact form accepts syntactically invalid email (?@gmail.com) violating RFC 5322 (Critical). BUG-04 — Unauthorized third-party ads (Oriflame) and referral links on a government institution website, correctly classified under Security / Content Integrity (Major). BUG-05 — Broken responsive layout with left-shifted content and missing padding on search results page (Major).

Checklist: Detailed mobile testing checklist (5 sections) covering UI/UX, functional logic, form validation, responsiveness, and resource security.

Level 2 — Android Studio Emulator Testing (Pixel 10, Android 17, Chrome): Three bug reports for zpolis.com.ua: BUG-01 — Article text squeezed to 100-150px column width with heading duplication (Major). BUG-02 — Missing client-side validation for Name (accepts //////) and Email (accepts /@gmail.com) fields in appointment modal (High). BUG-03 — Vertical scroll lock ("rubber band" effect) preventing upward scrolling from footer, documented with 82-frame GIF recording (Medium).

Level 3 — Diia (Дія) Application Test Matrix (20 Test Cases, ISTQB Standard): Formal test matrix across 4 categories: Functional Testing (5 cases — biometric auth, digital documents, QR generation, push notifications, logout), UI/Responsive Layout (5 cases — Dark Mode, orientation lock, font scaling, tap targets, loaders), Interrupt Testing (5 cases — incoming calls, low battery, network handover, internet disconnection, app backgrounding), Security Testing (5 cases — screenshot blocking, PIN attempts limit, task manager blur, field masking, root/jailbreak detection). Results: 18 Passed, 2 Failed (IN-04: no "connection lost" message; SEC-01: screenshot protection not working), 1 Not Tested (SEC-05: requires jailbroken device).

---

## Основні результати та практичні рішення

### 1 Баг-репорти на реальному iPhone (dpcozt.com.ua)
5 багів зафіксовано на iPhone 16 Pro (Safari, iOS 18): обрізання юридичного застереження (Critical — Legal Risk), зациклена SEO-перелінковка, прийняття невалідного Email, стороння реклама на державному сайті (Security), злам адаптивної сітки. Розроблено чек-ліст мобільного тестування (5 розділів).

### 2 Тестування через емулятор Android Studio
Налаштовано Android Virtual Device (Pixel 10, Android 17, API 37). Виявлено 3 баги на zpolis.com.ua: стиснення контенту, відсутність валідації форм, залипання скролу (з GIF-доказом на 82 кадри).

### 3 Матриця тестування додатку «Дія»
20 тест-кейсів за стандартом ISTQB у 4 категоріях. Знайдено 2 реальних дефекти: відсутнє повідомлення при обриві мережі (IN-04) та непрацюючий захист від скриншотів (SEC-01). Кейс SEC-05 чесно позначено як N/T через відсутність jailbreak-пристрою.

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек та внесено виправлення:

### Оцінка задач Beet Seed рівня (iPhone-баги):
> *"П'ять багів на реальному iPhone, і кожен перевірений. Особливо цінні знахідки: BUG-01 із позначкою «Critical (Legal Risk)» — ти правильно розпізнала, що обрізане застереження про паспорти старого зразка не просто візуальний глюк, а юридичний ризик для власників тварин. BUG-04 (стороння реклама на державному сайті) — це питання довіри та інформаційної безпеки установи, і ти влучно віднесла це до Component: Security / Content Integrity."*

### Рекомендація щодо BUG-02:
> *"Для BUG-02 (циклічна SEO-перелінковка) варто додати відео замість статичного скриншота, бо сам ефект «зациклення» найкраще демонструється в динаміці, послідовними кліками."*

### Оцінка задач Beet Sprout рівня (Емулятор):
> *"Ти успішно налаштувала емулятор Android Studio (Pixel 10, Android 17, API 37) — це саме той крок, на якому застрягли інші студенти. GIF-запис скролу (82 кадри) для BUG-03 — чудова відповідність вимозі завдання."*

### Виправлення за результатами рецензії:

**BUG-01 емулятора (Priority):** Ментор зазначила, що «Severity: Major / Priority: Major» — це повторення термінології. Priority зазвичай позначається шкалою Low/Medium/High/Critical, а не Severity-термінами. Виправлено на коректну Priority: High.

### Оцінка задач Mighty Beet рівня (Матриця «Дія»):
> *"Матриця з 20 тест-кейсів на реальному застосунку «Дія» за категоріями Functional/UI/Interrupt/Security — це вже рівень формального тест-плану за ISTQB. Найцінніше — ти знайшла два справжні Failed-результати на живому державному застосунку: IN-04 та SEC-01 — це реальні, відтворювані дефекти. Твоя примітка до SEC-05 — зразок чесного визначення межі тестового покриття, а не вигаданого результату."*

> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Мобільне тестування на реальному пристрої (Real Device Testing): Тестування мобільної версії сайту на iPhone 16 Pro з фіксацією дефектів, специфічних для мобільного viewport та touch-інтерфейсу.

Класифікація ризиків (Risk-based Bug Classification): Визначення бага як Legal Risk (BUG-01) та Security / Content Integrity (BUG-04) — вихід за межі стандартної UI-класифікації.

Тестування через емулятор (Android Emulator Testing): Налаштування Android Virtual Device у Android Studio та фіксація багів із GIF-доказами.

Формальна тестова матриця (Test Matrix / ISTQB): Побудова структурованої матриці з 20 тест-кейсів за 4 категоріями з чітким визначенням статусів Passed/Failed/N/T.

Чек-ліст тестування (Testing Checklist): Розробка деталізованого чек-ліста мобільного тестування з 5 розділів.
