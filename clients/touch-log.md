# 📒 Touch Log — UnderUndre Clients (UnderUndre repo)

**Назначение:** журнал касаний и ответов по клиентским разборам из `clients/` этого репо. Правила и карточки триггеров — Trigger Playbook v2.1 (`UndeRoute/.specify/templates/trigger-playbook.md`); таксономия Reason — там же. **Нет строки — касания не было.**

---

## 📥 Raw Log

Чекпоинты (Reply → Call → Discovery → Proposal → Won/Lost) = дата прохождения; пусто = не дошёл. Reason — только при Lost.

```csv
Date,Company,Trigger,Channel,Source,Reply,Call,Discovery,Proposal,Won,Lost,Reason
2026-11-06,Smart IT Power LLC (Ереван),07-pm-explosion,?,vacancy,2026-11-07,,,,,2026-11-07,LOST_STATUS_QUO
```

*(Smart IT Power: мемо-фасовка `clients/smpower/` (trigger-memo.md + wa.md), сигнал — синхронный найм .NET + Tech Writer + Manual QA, hh 139062931 / 138935605 / 138430147. Отказ получен 2026-11-07; причина не озвучена — записан код LOST_STATUS_QUO по умолчанию, уточнить при повторном контакте; заодно заполнить Channel и точную дату отправки.)*

| Date | Company | Trigger | Channel | Source | Reply | Call | Discovery | Proposal | Won | Lost | Reason |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2026-11-06 | Smart IT Power LLC (Ереван) | 07-pm-explosion | ? | vacancy | 2026-11-07 | | | | | 2026-11-07 | LOST_STATUS_QUO |

---

## 📈 Агрегат (заполняется раз в месяц; вердикты по триггеру — только после 30–50 касаний)

| Trigger | Sent | Replies | Reply % | Calls | Discovery | Won | Доминирующий Reason |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| 07-pm-explosion | 1 | 1 | 100%* | | | | LOST_STATUS_QUO |

*(*выборка 1 — статистической силы нет; цифра только для учёта, не для вердикта)*

---

## 🗓️ Заметки по лидам

- **Smart IT Power** — отказ без озвученной причины. Отраслевой дескриптор для кейса: «IT-компания в Ереване, синхронный найм .NET + Tech Writer + QA». Если паттерн «синхронный найм трёх ролей контура» повторится в touch-log ещё 2 раза на разных компаниях и хотя бы раз переживёт проверку — кандидат в Pattern Promotion Gate (3 сигнала / 3 окружения / ≥1 FP).
