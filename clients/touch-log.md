# 📒 Touch Log — UnderUndre Clients (UnderUndre repo)

**Назначение:** журнал касаний и ответов по клиентским разборам из `clients/` этого репо. Правила и карточки триггеров — Trigger Playbook v2.1 (`UndeRoute/.specify/templates/trigger-playbook.md`); таксономия Reason — там же. **Нет строки — касания не было.**

---

## 📥 Raw Log

Чекпоинты (Reply → Call → Discovery → Proposal → Won/Lost) = дата прохождения; пусто = не дошёл. Reason — только при Lost.

```csv
Date,Company,Trigger,Channel,Source,Reply,Call,Discovery,Proposal,Won,Lost,Reason
2026-11-06,Smart IT Power LLC (Ереван),07-pm-explosion,?,vacancy,2026-11-07,,,,,2026-11-07,LOST_STATUS_QUO
2026-11-06,Profitov.Partners (Тбилиси),07-pm-explosion,?,vacancy,2026-11-09,,,,,2026-11-09,LOST_STATUS_QUO
2026-11-08,Employcity (Москва),06-revops,hh,vacancy,2026-11-09,,,,,2026-11-09,LOST_STATUS_QUO
```

*(Smart IT Power: мемо-фасовка `clients/smpower/` (trigger-memo.md + wa.md), сигнал — синхронный найм .NET + Tech Writer + Manual QA, hh 139062931 / 138935605 / 138430147. Отказ получен 2026-11-07; причина не озвучена — записан код LOST_STATUS_QUO по умолчанию, уточнить при повторном контакте; заодно заполнить Channel и точную дату отправки.)*

*(Profitov.Partners: фасовка в undreplans `clients/Profitov-Partners/` (audit.md + employee-applying.md), сигнал — наём Junior Affiliate менеджеров в Тбилиси + аудит onboarding dispatch friction; отклик на вакансию Аффилейт менеджера с приложенным аудитом. Отказ ~2026-11-09; причина не озвучена.)*

*(Employcity: фасовка `clients/employcity/` (trigger-memo.md + workaround-audit.md + b2b-growth-manager-application-letter.md + demo-кейс расследования NGR), сигнал — найм B2B Growth Manager (верб. LEVEL_1_PROCESS_SOP, custom ATS FORBIDDEN). Отклик с приложенным Discovery и демо-кейсом отклонён ~2026-11-09; причина не озвучена.)*

| Date | Company | Trigger | Channel | Source | Reply | Call | Discovery | Proposal | Won | Lost | Reason |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2026-11-06 | Smart IT Power LLC (Ереван) | 07-pm-explosion | ? | vacancy | 2026-11-07 | | | | | 2026-11-07 | LOST_STATUS_QUO |
| 2026-11-06 | Profitov.Partners (Тбилиси) | 07-pm-explosion | ? | vacancy | 2026-11-09 | | | | | 2026-11-09 | LOST_STATUS_QUO |
| 2026-11-08 | Employcity (Москва) | 06-revops | hh | vacancy | 2026-11-09 | | | | | 2026-11-09 | LOST_STATUS_QUO |

---

## 📈 Агрегат (заполняется раз в месяц; вердикты по триггеру — только после 30–50 касаний)

| Trigger | Sent | Replies | Reply % | Calls | Discovery | Won | Доминирующий Reason |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| 07-pm-explosion | 2 | 2 | 100%* | | | | LOST_STATUS_QUO |
| 06-revops | 1 | 1 | 100%* | | | | LOST_STATUS_QUO |

*(*выборка 3 — статистической силы нет; цифры только для учёта, не для вердикта)*

---

## 🗓️ Заметки по лидам

- **Smart IT Power** — отказ без озвученной причины. Отраслевой дескриптор для кейса: «IT-компания в Ереване, синхронный найм .NET + Tech Writer + QA». Если паттерн «синхронный найм трёх ролей контура» повторится в touch-log ещё 2 раза на разных компаниях и хотя бы раз переживёт проверку — кандидат в Pattern Promotion Gate (3 сигнала / 3 окружения / ≥1 FP).
- **Profitov.Partners** — двойной маршрут (аудит + отклик на вакансию с релокацией в Тбилиси) отклонён. Дескриптор: «iGaming affiliate-сеть, синхронный наём junior-менеджеров + конференции». Триггер #7/семейство найма: +1 сигнал.
- **Employcity** — отклик на вакансию B2B Growth Manager (с Discovery: LEVEL_1_PROCESS_SOP, custom ATS FORBIDDEN + демо-кейс NGR-расследования) отклонён. Дескриптор: «рекрутинговое агентство, найм growth-роли». Сигнал #6: +1.
- **Урок серии:** три отказа за неделю при 100% reply rate — касания долетают и читают быстро, но конверсии в разговор нет. Все три — refused без озвученной причины; при следующей пачке касаний попробовать CTA с более низким трением (вопрос-выбор вместо «могу показать») и сравнить reply→качество ответа.

---

## 🗓️ Pattern Promotion Gate счётчик

- «Синхронный найм ролей контура (dev/QA/writer или junior-менеджеры)»: Smart IT Power + Profitov = **2 / 3 сигналов, 2 / 3 окружений, 0 FP** — гейт не пройден, паттерн не публиковать.
- «Найм growth/RevOps роли при операционном засоре»: Employcity = **1 / 3**.
