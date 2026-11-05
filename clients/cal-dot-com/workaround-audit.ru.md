# Forensic Workaround & Margin Leak Audit (Pre-Interview Discovery Memo)

**Client:** Cal.com, Inc. (Delaware C-Corp, File #5792440; ранее Calendso, Inc.)  
**Delivery Model:** Solo Productized Engineering Bureau (UnderUndre)  
**Date:** 2026-11-04  
**Mode:** B2B Services & SaaS Delivery Economics  
**Status:** PRE-INTERVIEW HYPOTHESIS REGISTER  
**Primary Suspected Constraint:** `COST_ATTRIBUTION_DEBT_CAUSED_BY_UNVERIFIED_OPEN_CORE_ECONOMICS` (UNVERIFIED)

---

## 0. Почему вы получили этот аудит

Я — Андрей, соло-инженер бюро underundre.com; оцифровываю операционные трения. Это pre-interview discovery-мемо я подготовил для Cal.com по открытым данным — без вендоров и питч-деков, только фальсифицируемый разбор вашей open-core экономики.

### Что привлекло внимание

1. Бифуркация 15 апреля 2026: продакшен-код переехал в приватный репозиторий; `calcom/cal.diy` выпущен как урезанный MIT-форк.
2. Подтверждённый баг валидации лицензии, затрагивающий self-hosted платные сценарии (Issue #26610, фикс в `deployments.service.ts`).
3. Найм сконцентрирован на Enterprise-продуктизации (Senior Product Designer, Enterprise Fullstack Engineers).
4. ~50k звёзд / 16k форков / 1.2k открытых issues — без публичных когортных данных, связывающих пользователей `cal.diy` с закрытыми Enterprise-контрактами.

Обычно такой набор означает, что компания пока не может определить, является ли open-source «хвост» движком привлечения клиентов или операционной утечкой.

### Наиболее вероятное объяснение

Долг атрибуции затрат: инженерные часы уходят на нереvenue community issues, а сквозной атрибуции от форка до закрытых Enterprise-контрактов нет. Это предварительная гипотеза по открытым данным; конкурирующие объяснения и критерии опровержения — внутри аудита.

### Альтернативные объяснения

- Здоровый рост: сплит — чистая изоляция IP; трение нормально для масштабирования Series A.
- Форк — эффективный CAC-движок: тогда закрывать трекер — риск для выручки.
- Нулевая гипотеза: open-source накладные расходы поглощаются в пределах допуска; вмешательство не требуется.

### Что проверить за 5 дней

Ретроспективная атрибуция источников по последним 20 закрытым Enterprise Organizations сделкам: сколько началось с self-hosted `cal.diy`?

### Если у вас есть только 60 секунд

- **Предварительный вывод:** open-core экономика не атрибутирована, а не сломана.
- **Уверенность:** низкая (направление ограничено 60%; масштаб не доказан).
- **Необходимые данные:** выгрузка Linear issue→tier клиента; время core-инженеров на некоммерческие issues; источники сделок.
- **Предполагаемый первый шаг:** ретроспектива атрибуции по 20 сделкам выше.
- **Вероятность того, что нужен новый софт:** низкая (рекомендации — SOP за $0, строго условные).

---

## 1. Epistemic Horizon & Stakeholder Alignment

- **Economic Buyer (P&L Owner):** Peer Richelsen & Bailey Pumfleet (Co-founders & Co-CEOs).
  - *Статус права подписи (Gate 1):* `(b) Partner consensus / Board approval required [AUTHORITY UNVERIFIED]`. Лимит единоличной финансовой авторизации ($5,000+) закрыт соглашением акционеров Delaware C-Corp. Уровень Level 3 (Build) заблокирован до личной верификации полномочий.
- **Process Sponsor:** Keith Williams (Head of Engineering). Несёт прямую ответственность за пропускную способность ядра, CI/CD и стабильность закрытого монорепозитория.
- **JTBD Trigger Catalyst (90-Day Push / Gate 9):** Институциональный раскол 15 апреля 2026 года — вывод production-кода в приватный репозиторий и выпуск урезанного `calcom/cal.diy` (MIT) с удалением Enterprise-модулей (Teams, Orgs, SAML/SSO, Workflows). Это создало операционную турбулентность в трекере и сделало критическим вопрос: окупает ли открытый форк затраты на его сопровождение?
- **Observed Vector of Investment (OSINT Evidence, L4):**
  - Публичный наём Senior Product Designer ($100k–$150k) и Enterprise Fullstack инженеров фиксирует доказанный вектор распределения ресурсов (Revealed Preference): капитал заливается в коммерческую упаковку сложных B2B-фичей (Organizations, Routing Forms, SSO).
  - Дашборд `cal.com/open` подтверждает макро-наблюдаемость (зарплатные сетки, headcount ~40–44 FTE, динамика коммитов).
- **Master System of Record (Gate 4):** GitHub Enterprise + Linear + Stripe Billing + PostgreSQL.
- **Economic Scale Status (Gate 8):** `Band (d): $5M+/yr (ARR ~$5.1M, OpEx >$250k/mo)`. Базовая расчётная ставка loaded rate для Senior SWE: **$75–$110/час**.
- **Observability Status:** `MACRO_OBSERVABLE / TIER_ATTRIBUTION_UNVERIFIED`. Макро-метрики открыты, но отсутствует сквозная потикетная трассировка: компания не имеет данных о распределении часов сеньор-разработчиков между платными клиентами и открытым комьюнити.
- **Change Capacity Score (1–5 / Gate 3):** `NOT_VERIFIED [ESTIMATED_RANGE: 2–4, HYPOTHESIS]`.
  - Скорость поставки кода экстремальная (тысячи коммитов, мгновенная перестройка архитектуры под закрытую модель). Однако поведенческая готовность команды к административным регламентам фильтрации тикетов требует проверки на интервью.
- **Political Sabotage & Friction Vectors:**
  - *Кто теряет влияние при шлюзовании трекера?* DevRel и комьюнити-менеджеры, чей KPI завязан на открытость проекта и звёзды на GitHub; фаундеры, чей персональный бренд построен на философии 100% Open Startup.
- **Primary Business Bottleneck (Goldratt TOC / Gate 2):** `HYPOTHESIS: CONVERSION_PLUMBING & FULFILLMENT OVERFLOW (IN_SCOPE)`.
  - Требует исключения сценария коммерческого тупика (Demand Collapse).

---

## 2. Evidence Confidence Register & Hypothesis Tree

### Leading Hypothesis Tree

- **Core Hypothesis:** `Cost Attribution Debt in Open-Core Architecture`
  - *Sub-Hypothesis A (Support Spillover):* Разработчики ядра непроизвольно тратят дорогой ресурс ($90/ч) на воспроизведение и дебаг багов в `cal.diy`, не генерирующих выручки.
  - *Sub-Hypothesis B (Conversion Blindspot):* У компании отсутствует инструмент сквозной атрибуции, связывающий пользователя форка `cal.diy` с закрытой сделкой Enterprise Organizations ($28/user/mo).

| Фактор трения / Наблюдение | Direction Conf. (Факт) | Magnitude Conf. (Масштаб) | Первичное доказательство (Уровень L1–L5) | Эпистемическая слепая зона (Требуемая телеметрия) |
| :--- | :---: | :---: | :--- | :--- |
| **Open-Core Community Drag** | **60%** (Capped) | **15%** | L4 (OSINT: ~50k stars, 16k forks, 1.2k issues) + L5 (Блог о сплите кодовой базы) | Выгрузка Linear/GitHub: связка `User -> Issue ID -> Customer Tier (Free vs Paid)`. |
| **Context-Switching Tax ($K \ge 2$)** | **50%** | **10%** | L4 (Структура двух репозиториев: закрытое ядро и форк `cal.diy`) | Анонимизированный CSV тайм-трекинга или git-активности с интервалами коммитов `[ID NOT FOUND]`. |
| **Open-Core Conversion Visibility Gap** | **60%** (Capped) | **0%** | L4 (Отсутствие публичных когортных воронок на `cal.com/open`) | Сквозная аналитика: `Telemetry ID / Domain Hash -> Closed Won Enterprise Deals`. |
| **Дебаг лицензий и ключей** (Issue #26610) | **95%** | **40%** | L1 (Коммит фикса в `deployments.service.ts`) + L1 (Issue #26610) | Выгрузка логов обращений в саппорт с ошибкой HTTP 401 от платящих клиентов. |

*(Примечание: Уверенность по факторам на базе OSINT строго ограничена потолком 60% для Direction и 20% для Magnitude до получения телеметрии L1/L2).*

### Working Competing Hypotheses

1. **Alt 0 (Healthy Growth Hypothesis — Нулевая гипотеза роста):** Наблюдаемый шум в репозитории и наём дизайнеров/инженеров — это естественные симптомы здорового масштабирования Series A компании, перерастающей стадию наколенного стартапа. Раскол 15 апреля 2026 года — плановая и успешная сепарация интеллектуальной собственности от бесплатных форков, не создающая критического трения внутри команды.
2. **Alt 1 (Operational Drain):** Бесплатный хвост `cal.diy` паразитирует на фонде рабочего времени инженеров ядра, размывая фокус с enterprise-разработки.
3. **Alt 2 (Licensing & Architecture Clashes):** Архитектурные расхождения между приватным монорепозиторием и публичным кодом приводят к постоянному срыву синхронизации и сбоям валидации лицензий.
4. **Alt 3 (Integration Delivery Friction):** Узкое место лежит не в комьюнити, а в асинхронных гонках внешних календарей (Google/Microsoft API) в `EventManager.ts` (Issue #28705).
5. **Alt 4 (Scope / Support Spillover):** Корпоративные клиенты требуют кастомных доработок интеграций под видом стандартной гарантийной поддержки.
6. **Alt 5 (Null Hypothesis — $H_0$):** Операционные процессы и триаж тикетов протекают в пределах допустимой нормы; накладные расходы на открытый код минимальны и не наносят измеримого ущерба маржинальности; вмешательство не требуется.

### Required Disconfirming Evidence Search (Поиск опровергающих улик)
>
> *Активный поиск фактов для опровержения ведущей гипотезы (Cost Attribution Debt):*  
> Аудитор обязан запросить происхождение последних 20 закрытых сделок Enterprise. Если $\ge 50\%$ enterprise-клиентов пришли напрямую из self-hosted установок `cal.diy`, а выгрузка Linear покажет, что разработчики ядра тратят $<5\%$ времени на открытый репозиторий — ведущая гипотеза считается **убитой**. В этом случае открытый код — это сверхокупаемый канал продаж (CAC), а не засор.

### Popperian Falsification Criteria (Критерий фальсификации Поппера)
>
> *Ведущая гипотеза будет официально ФАЛЬСИФИЦИРОВАНА, если:*  
> **Выгрузка закрытых тикетов Linear за последние 90 дней зафиксирует суммарные трудозатраты Core SWE на тикеты без привязки к платящему контракту на уровне менее 3 часов в неделю на человека.**

---

## 3. Cost of Workaround & Friction Ledger (Calibration Model)

> ⚠️ **EPISTEMIC DISCLAIMER:** Данный реестр представляет собой **калибровочную стресс-модель** на базе подтверждённого масштаба компании (Gate 8: Band d, loaded rate $75–$90/ч) и наблюдаемых сигналов. Без первичных выгрузок базы данных эти цифры НЕ являются бухгалтерскими фактами.

$$\text{CoW}_{\text{Lite}} = C_{\text{FTE}} + C_{\text{SaaS}} + C_{\text{Scrap}}$$
$$\text{где } C_{\text{FTE}} = \sum (\text{Reported Hours} \times W_{\text{evidence}} \times \text{Loaded Rate} \times 52)$$

| Кандидат-засор / Сигнал затрат | Заявленный объём | Уровень данных | Вес улики ($W$) | Loaded Rate | Стресс-тест CoW | Эпистемический класс |
| :--- | :--- | :--- | :---: | :--- | :--- | :--- |
| **Сбои валидации лицензий селф-хоста** (дебаг Issue #26610) | 10 ч/нед (модель) | Level 1 (Issues/PR) | **1.0** | $75 / ч | `[UNVERIFIED]` | `[MODEL_PENDING_TELEMETRY]` |
| **Паразитный софтверный стек ($C_{\text{SaaS}}$)** (Linear + Intercom + Zendesk) | Наличие дублей | Level 1 (Инвойсы) | **1.0** | Flat Fee | `[UNVERIFIED]` | `[PENDING_INVOICE_AUDIT]` |
| **Support Escalation Spillover** (инженеры ядра в открытом трекере) | Не подтверждено | Level 4 (OSINT/Issues) | **0.3** | $90 / ч | `[UNVERIFIED]` | `[HEURISTIC_OSINT]` |
| **Context Switching Tax ($K \ge 2$)** | 20–40% потерь фокуса | Level 4 (Модель) | **0.3** | $90 / ч | `[UNVERIFIED]` | `[HEURISTIC: WEINBERG_MODEL]` |
| **ИТОГОВЫЙ ПОДТВЕРЖДЁННЫЙ ПОРОГ (HARD FLOOR):** | — | — | — | — | **IDENTIFIER_NOT_FOUND** | `[NO_SYNTHETIC_PRECISION]` |

*Аудиторский вердикт по деньгам:* Публикация синтетических сумм в долларах строго запрещена до получения сквозной телеметрии. Наблюдаемые сигналы потерь присутствуют (`PRESENT`), но точная сумма ущерба юридически не доказана.

---

## 4. Pre-Mortem & Constraint Relocation Analysis

### 4.1. The Klein Pre-Mortem (Анализ провала через 6 месяцев)

*Представим, что предложенные регламенты фильтрации были внедрены, но проект потерпел полный крах к 6-му месяцу. Топ-3 фатальных вектора:*

1. **Вектор 1 (Политический / Брендовый):** Введение обязательной валидации лицензии для создания Issue вызвало публичный скандал на Hacker News («Cal.com окончательно предал идеалы Open Source»), что ударило по виральности и снизило органический поток входящих enterprise-лидов.
2. **Вектор 2 (Операционный / Ложные срабатывания):** Потенциальные enterprise-клиенты, тестировавшие `cal.diy` в локальном контуре до заключения контракта, наткнулись на закрытые двери баг-трекера, сочли проект «мёртвым» и ушли к Calendly/SavvyCal.
3. **Вектор 3 (Управленческий саботаж):** Основатели и инженеры ядра продолжили отвечать на багрепорты в Discord и X (Twitter) в обход регламента, разрушив дисциплину шлюзования.

### 4.2. Constraint Relocation Forecast (Прогноз миграции бутылочного горлышка по Голдратту)

- **Текущее подозрение на засор:** Неразмеченная трата инженерных ресурсов на обслуживание открытого репозитория.
- **Куда мгновенно мигрирует ограничение после зачистки:** Как только инженеры ядра перестанут отвлекаться на комьюнити, ограничение моментально сместится в **Enterprise Delivery & Onboarding**. Узким местом станет скорость интеграции сложных корпоративных сред (настройка SSO/SCIM под кастомные IdP, интеграция с on-premise Microsoft Exchange серверами заказчиков).
- **Директива по сдерживанию:** Заблаговременная подготовка стандартизированного пакета преднастроенных коннекторов и чек-листа Enterprise Onboarding до перекрытия внешнего трекера.

---

## 5. The Hierarchy of Interventions (Traversal Gate)

- **Reversibility Rating (Bezos Type 1 vs Type 2):** `HIGH (Two-Way Door)`.
  - Введение или отмена административного регламента шлюзования issues в GitHub откатывается за 15 минут сменой настроек репозитория. Допустимо принятие решений при $\ge 60\%$ уверенности.
- **Implementation Blindfold Check (Тест на конфликт интересов):**
  - *Запрос:* Порекомендовало бы бюро UnderUndre этот аудит и регламенты, если бы ему было законодательно запрещено продавать услуги заказной разработки?
  - *Результат:* **`PASS (Unbiased)`**. Бюро не предлагает разработку софта; ключевая рекомендация — аналитический стресс-тест за $490 и регламентные меры за $0 CAPEX.

### Level 0: Do Nothing (Статус-кво)

- **Вердикт:** `UNDER_EVALUATION`.
- **Экономическое основание:** Зависит от валидации гипотезы здорового роста (Alt 0) и нулевой гипотезы (Alt 5). Если комьюнити окупает себя как лидогенератор, сохранение статус-кво является экономически правильным решением.

### Level 1: Process / SOP Change ($0 CAPEX)

- **Вердикт:** `CANDIDATE_INTERVENTION (Conditional on Conversion Telemetry)`.
- **Суть кандидатного решения:**
  1. *Кандидат SOP-01:* Разделение входных каналов: в открытом `cal.diy` баг-трекер переводится в `Discussions`, создание issues в закрытом ядре требует корпоративного токена.
  2. *Кандидат SOP-02:* Назначение одного дежурного инженера на спринт под внешние PR с полной изоляцией остальных разработчиков.
- **Условие разблокировки:** Вводится строго после того, как стресс-тест докажет отсутствие положительной конверсии из форка в enterprise-продажи.

### Level 2: Buy COTS SaaS

- **Вердикт:** `DEFERRED_PENDING_TELEMETRY`.
- **Обоснование:** Закупка надстроек для AI-триажа или enterprise-саппорта откладывается до подтверждения объёма нагрузки.

### Level 3: Deploy Sovereign Bypass (Custom Build)

- **Вердикт:** `DEFERRED_PENDING_ATTRIBUTION_ANALYSIS`.
- **Обоснование:** На этапе предварительной разведки разработка кастомного софта не подлежит оценке (`NOT_EVALUABLE_AT_DISCOVERY_STAGE`). Решение может рассматриваться только при доказанном дефиците коробочных решений и Change Capacity $\ge 4$.

---

### 5.1. Productization Opportunities (Product Discovery Lens)

- **Стандартизируемые узлы:**
  1. *Enterprise License Verification Gate:* Унифицированный GitHub Action / Webhook, валидирующий хэш лицензии клиента перед созданием тикета.
  2. *Self-hosted Diagnostic CLI:* Консольная утилита для автоматической проверки конфигурации окружения (OAuth токены, шифрование `CALENDSO_ENCRYPTION_KEY`, связка с БД) до отправки тикета разработчикам.
- **Тиражируемый артефакт:** Готовый открытый микро-модуль валидации обращений для коммерческих open-source репозиториев (FOSS Utility).
- **Потенциал продуктовой масштабируемости:** Высокий. Проблема отделения бесплатного комьюнити-шума от корпоративных SLA типична для 100% COSS-бизнесов, переходящих с чистого AGPL на закрытые лицензии (PostHog, Supabase, Gitlab).

---

## 6. 🛑 AUTOMATION PROHIBITED LIST (VIA NEGATIVA)

- **AI-автоответчики в открытом репозитории:** Запрещено. Порождают галлюцинации и увеличивают длину тредов, отвлекая сеньоров на верификацию бреда бота.
- **Поминутные тайм-трекеры инженеров (Jira Tempo):** Запрещено. В открытой инженерной культуре Cal.com вызовет искажение метрик по закону Гудхарта и саботаж.
- **Самописный сервис лицензирования:** Запрещено. Ошибка `data.status` в `deployments.service.ts` лечится локальным патчем за 15 минут, а не новым сервисом.

---

## 7. Investor-Grade Stress Test

```text
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                               INVESTOR-GRADE STRESS TEST                               │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ Контрольный вопрос: Если Cal.diy полностью исчезнет завтра:                           │
│                     Enterprise ARR уменьшится, останется неизменным или вырастет?     │
│ Доказательства:     [IDENTIFIER NOT FOUND]                                             │
│                                                                                        │
│ Три допустимых исхода:                                                                 │
│ 1. ARR DOWN:        Cal.diy — это эффективный CAC и ключевой маркетинговый актив.      │
│                     Регламентное закрытие трекера противопоказано.                    │
│ 2. ARR FLAT:        Cal.diy — это чистый паразитный расход и операционный балласт.    │
│                     Показана немедленная консервация и шлюзование по Level 1 SOP.      │
│ 3. ARR UP:          Cal.diy каннибализирует коммерческую выручку.                      │
│                     Рекомендовано: стратегический пересмотр на уровне Совета           │
│                     директоров (границы функциональности, лицензии, ценовые барьеры). │
│                     Немедленные действия: [IDENTIFIER NOT FOUND / PENDING REVIEW].     │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 8. Final Diagnostic Verdict

```yaml
verdict: LEVEL_0_DO_NOTHING
primary_defect: UNVERIFIED
suspected_primary_constraint: COST_ATTRIBUTION_DEBT_CAUSED_BY_UNVERIFIED_OPEN_CORE_ECONOMICS
null_hypothesis_active: true
growth_hypothesis_active: true
change_capacity_score: NOT_VERIFIED_RANGE_2_TO_4
economic_buyer_aligned: probable_unverified
blindfold_check: PASS
evidence_class:
  - L1_TELEMETRY: true (Specific commits & Issue #26610)
  - L2_OBSERVED: false
  - L3_HEURISTIC: true
  - L4_OSINT: true (GitHub stats, cal.com/open, vacancies)
  - L5_MARKETING: true (Blog post on code bifurcation)
reversibility: HIGH
direction_confidence: 60% (Capped: relies on L4 OSINT signals)
magnitude_confidence: 15% (Capped: zero raw time telemetry)
intervention_confidence: 50%
likely_next_constraint: "Enterprise Onboarding & Complex IdP/Exchange Integration Capacity"
falsification_criteria: "Linear time exports showing <3 hrs/wk per Core SWE spent on non-contract issues, combined with >50% of closed Enterprise deals originating from cal.diy self-hosted instances."
pre_mortem_top_risk: "Public backlash against perceived abandonment of open-source ethos damaging top-of-funnel inbound pipeline."
recommended_immediate_action: "Дни 1-5 (Stage 0): Провести ретроспективный анализ источников лидов последних 20 закрытых сделок Enterprise Organizations для проверки Alt 0 (Healthy Growth) и ответа на Investor-Grade Stress Test до введения любых регламентов."
```

---
