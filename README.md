Чудово, починаємо! Ось перший файл з архіву — README.md, який пояснює принцип роботи проєкту, інструкцію з використання та загальну структуру. Скопіюй його в корінь репозиторію Guard_RF:

---

📄 README.md

`markdown

Guard_RF — Універсальний модуль контролю підключення антени по RF

🛰️ Призначення

Цей модуль дозволяє визначати наявність RF-випромінювання з високочастотного тракту (через порт 3 циркулятора) для керування логічною лінією EN. Застосовується у схемах типу глушників GNSS, передавачів, тестерів та інших ВЧ-пристроїв.

---

⚙️ Принцип дії

1. Port 1 циркулятора: вихід з підсилювача  
2. Port 2: підключення до антени  
3. Port 3: у разі поганого узгодження або відсутності антени — на цей порт надходить відбитий сигнал  
4. Схема детектора:
   - BAT15-03W детектує RF-сигнал
   - RC-фільтр формує постійну напругу
   - ОП-компаратор порівнює з Vref (~0.2 В)
   - Якщо RF є → EN = HIGH, інакше EN = LOW

---

📐 Склад схеми

- BAT15-03W — Шотткі-діод
- TLV9001 або MCP6001 — ОП-компаратор
- R, C — RC-ланцюги на виході діода
- R3/R4 — подільник напруги для формування Vref
- Живлення: +5 В
- EN вихід: TTL-рівень, струм до 10 мА

---

📦 Каталоги

`
KiCad/         → схема та розведення плати
SPICE/         → симуляція реакції діода на RF-сигнал
BOM/           → перелік елементів
doc/           → PDF-файли зі схемами та описом
`

---

🧪 Частотний діапазон

> 300 МГц – 5.8 ГГц  
Перевірено в моделюванні та емпірично, ефективне детектування в усьому цьому діапазоні.

---

📥 Як використовувати

1. Підключи вихід підсилювача → порт 1 циркулятора
2. Порт 2 → до антени
3. Порт 3 → на вхід схеми (через C ~100 пФ)
4. Сигнал EN підключи до лінії керування DC/DC, PA, MCU тощо
5. Змінюй порогову напругу Vref залежно від діапазону та рівня потужності

---

🛡️ Ліцензія

Цей проєкт поширюється під ліцензією MIT.

---

Розробка: Віталій • GitHub: github.com/Vitaliy977
`

