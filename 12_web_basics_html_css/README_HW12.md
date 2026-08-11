# Основи web (HTML, CSS). Кодування символів (Завдання №12)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW12_Web_Basics_HTML_CSS_Encoding_Hurtova.pdf)

---

## English Summary

Project Overview:  
This repository contains Homework #12 for the Software Testing and QA course. The assignment covers web fundamentals (HTML, CSS), bug reporting on a live website, cross-browser testing, and character encoding analysis using Chrome DevTools.

Key Scope & Topics Covered:

Bug Reports for headhunterhairstyling.com (3 Reports): Three bug reports written for a Wix-based website. SCRUM-27: Platform behavior observation documenting Wix background telemetry (frog.wix.com, bulklog, fedopsLogger) — reclassified from bug to informational platform observation per mentor feedback, as continuous background requests are standard Wix architecture behavior. Severity: None/Information. SCRUM-28: Non-clickable footer brand text "HeadHunter Hairstyling" — implemented as `<span>` instead of `<a>` tag, missing click event handlers, cursor shows text-select instead of pointer. Includes DevTools analysis and recommended fix code. Severity: Low. SCRUM-29: Draggable static images — missing `draggable="false"`, `user-select: none`, `-webkit-user-drag: none` CSS properties on decorative images. Severity: Low.

HTML/CSS Homework (3 Styling Methods): Single HTML document demonstrating all three CSS connection methods — Inline (style attribute on `<button>` element with red background), Internal (in HEAD via `<style>` tag with page background and block styling), External (separate style.css file with blue block styling via `<link>` tag).

Cross-Browser Testing Report: Chrome vs Safari (macOS) comparison — identical rendering confirmed, no differences found. All three CSS styling methods correctly rendered in both browsers. Interactive elements (cursor changes, text selection) behave identically.

Character Encoding Analysis (4 Websites): DevTools-based analysis of HTML source code (Elements tab) and server response headers (Network tab) for beetroot.academy (UTF-8 — meta charset and server header match), microseniors76.com (ISO-8859-1 — server returns no charset, browser uses meta http-equiv fallback), tennis-warehouse.com (macintosh in code / ASCII in server headers — discrepancy identified), fidelity.com (UTF-8 — no meta charset tag, server header provides charset).

---

## Основні результати та практичні рішення

### 1 Баг-репорти для headhunterhairstyling.com
Написано 3 баг-репорти для сайту на платформі Wix: SCRUM-27 (спостереження щодо фонової телеметрії платформи — перекласифіковано з бага на інформаційну замітку), SCRUM-28 (неклікабельний текстовий логотип у футері — з технічним обґрунтуванням через DevTools та кодом рекомендованого фіксу), SCRUM-29 (перетягування статичних зображень — з аналізом відсутніх HTML-атрибутів та CSS-властивостей).

### 2 HTML-документ з трьома способами CSS
Створено HTML-документ, що демонструє Inline (вбудований у тег), Internal (у розділі HEAD) та External (у зовнішньому .css файлі) способи підключення стилів. Файли додані в архіві homework.zip.

### 3 Крос-браузерне тестування
Проведено порівняльне тестування HTML-документа в Chrome та Safari (macOS). Результат — ідентичне відображення, жодних розбіжностей не виявлено.

### 4 Аналіз кодування символів (4 сайти)
За допомогою Chrome DevTools (вкладки Elements та Network) визначено кодування для 4 сайтів. Виявлено розбіжність між кодуванням у meta-тегу та серверному заголовку на сайті Tennis Warehouse (macintosh vs ASCII).

---

## Менторська підтримка та вдосконалення рішення

Робота пройшла професійне рецензування, в результаті якого було отримано цінний фідбек та внесено виправлення:

### Оцінка задач Beet Sprout рівня (Аналіз кодування):
> *"Це одна з найсильніших робіт у групі: ти використала не лише вкладку Elements, а й мережеві заголовки Response Headers — і саме це дозволило зафіксувати головну знахідку tennis-warehouse.com, де код сторінки каже macintosh, а сервер — ASCII."*

### Оцінка задач Must have рівня (Баг-репорти):
> *"SCRUM-28 і SCRUM-29 — це зразкові баг-репорти рівня Strong Junior: ти не просто описала симптом, а дійшла до первинної технічної причини — відсутній тег &lt;a&gt;, відсутній атрибут draggable='false' — і додала конкретний код виправлення."*

### Виправлення за результатами рецензії:

**SCRUM-27 (перекласифікація):** Ментор зазначила, що SCRUM-27 не є помилкою в класичному розумінні. Для сайтів на Wix постійні фонові запити (frog.wix.com, bulklog, fedopsLogger) — це стандартна поведінка платформи. Звіт перекласифіковано з баг-репорту на «Технічне спостереження / Platform Behavior» зі Severity: None / Information.

### Оцінка крос-браузерного тестування:
> *"Скріншот-порівняння Chrome vs Safari додає доказовості — це правильний підхід до фіксації результатів крос-браузерного тестування."*

> — Nadiia Ovsiannikova (Ментор)

---

## Ключові навички, продемонстровані в роботі

Баг-репортинг з технічним обґрунтуванням (Bug Reporting): Написання баг-репортів із використанням Chrome DevTools для ідентифікації кореневих причин (вкладки Elements, Styles, Event Listeners, Network) та наданням конкретного коду виправлення.

Основи HTML та CSS (Web Fundamentals): Практичне розуміння трьох способів підключення стилів (Inline, Internal, External) та їх пріоритетності, створення валідного HTML-документу.

Крос-браузерне тестування (Cross-Browser Testing): Порівняльний аналіз відображення веб-сторінки у різних браузерах (Chrome, Safari) з фіксацією результатів.

Аналіз кодування символів (Character Encoding Analysis): Використання DevTools для комплексного аналізу кодувань через два незалежні джерела (HTML-код та серверні заголовки) з виявленням розбіжностей.
