# Домашня робота: Тестування API за допомогою SoapUI (Завдання №18)

> Оригінальний файл роботи: [Переглянути виконану роботу у PDF](./HW18_API_Testing_SoapUI_Hurtova.pdf)
> SoapUI-проект: [Homework18soapuiproject.xml](./Homework18soapuiproject.xml)

---

## English Summary

Project Overview:  
This repository contains Homework #18 for the Software Testing and QA course. The assignment covers SOAP API testing using SoapUI: importing a WSDL schema, creating parameterized test cases with Custom Properties, building automated assertions, discovering a real backend bug, and performing a comparative analysis of SoapUI vs Postman.

Key Scope & Topics Covered:

TestSuite Structure (4 TestCases, 16 Steps, 48+ Assertions): Based on the imported CountryInfoService WSDL schema, four TestCases were created covering operations: CapitalCity, CountryISOCode, CountryCurrency, and CountriesUsingCurrency. Each TestCase contains 4 test steps (2 positive + 2 negative), totaling 16 steps with minimum 3 assertions each.

Dynamic Parametrization via Custom Properties: All test data injected through SoapUI Custom Properties using context syntax ${#TestCase#VariableName}, with minimum 2 variables per step: input value for XML tag and expected result for assertion validation. No hardcoded data in XML request bodies.

Assertions (3 per Step): Valid HTTP Status Codes (200 OK), Not SOAP Fault (no SOAP protocol-level errors), Contains (dynamic content validation comparing actual response against ${#TestCase#ExpectedResult}).

Bug Report — BUG-001: CountryISOCode returns "AX" (Aland Islands) ISO code when empty country name is passed as parameter. Backend performs incorrect database query instead of returning "No country found by that name" error. Classified as Minor severity / Medium priority — backend logic / database query validation issue.

Comparative Analysis — SoapUI vs Postman: Practical comparison across protocols (SOAP/XML vs REST/JSON), assertion creation (visual click-based vs JavaScript code), variable syntax (${#TestCase#Var} vs {{var}}), with pros/cons table and tool positioning summary.

---

## Основні результати та практичні рішення

### 1 Структура тестового набору
4 TestCase на основі WSDL-схеми CountryInfoService: CapitalCity, CountryISOCode, CountryCurrency, CountriesUsingCurrency. 16 тестових степів (8 позитивних + 8 негативних) з мінімум 3 асертами кожен.

### 2 Параметризація та асерти
Динамічна параметризація через Custom Properties (${#TestCase#Variable}). Три обов'язкових асерти: Valid HTTP Status Codes, Not SOAP Fault, Contains з динамічним ExpectedResult.

### 3 Знайдений дефект (BUG-001)
Метод CountryISOCode повертає ISO-код «AX» (Аландські острови) при передачі порожнього параметра замість повідомлення «No country found». Severity: Minor, Priority: Medium.

### 4 Порівняння SoapUI та Postman
Практичний порівняльний аналіз за критеріями: протоколи, асерти, змінні, плюси/мінуси та основне призначення кожного інструменту.

---

## Ключові навички, продемонстровані в роботі

Тестування SOAP API (SOAP/WSDL Testing): Імпорт WSDL-схеми, створення TestSuite з TestCase та тестовими степами, налаштування автоматичних асертів через візуальний конструктор SoapUI.

Параметризація тестових даних (Custom Properties): Впровадження динамічних змінних замість статичних даних у XML-запитах із використанням контекстного синтаксису SoapUI.

Баг-репортинг на рівні бекенду (Backend Bug Reporting): Виявлення та документування дефекту в бізнес-логіці серверної обробки запитів (некоректна вибірка з БД при порожньому параметрі).

Порівняльний аналіз інструментів (Tool Comparison): Практичне порівняння SoapUI та Postman за ключовими критеріями з обґрунтуванням сфер застосування кожного.
