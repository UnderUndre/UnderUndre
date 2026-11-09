---
description: Perform a forensic Workaround, Process-Friction & Margin-Leak Audit ($350–$490 Tripwire / Product 0). Enforces Principle XVI Telemetry Triage (GREEN/YELLOW/RED), Owner ≠ Authority separation, subtractive epistemology, L1-L5 evidence weighting, Alt 0 Growth hypothesis, Vacancy Synchrony, Pre-Mortem, Stress-Test Hypothesis Register, Cross-Validation Note, Domain Asset Engine, and Product 0→1→2 commercial lifecycle routing. Output is a two-layer memo - a ≤250-word Executive Narrative front layer (§0) + full forensic body.
handoffs:
  - label: Write Bypass Spec
    agent: speckit.specify
    prompt: Draft the technical specification for the single approved Level 3 (Build) intervention from this audit
    send: true
  - label: Review Workaround Audit
    agent: speckit.speckit-discovery-review
    prompt: Independently verify the TDABC math, evidence weights, epistemic ceilings, buyer alignment, and Out-of-Scope triggers
  - label: Write Trigger Memo
    agent: speckit.narrative
    prompt: Translate this finished audit into the mandatory ≤250-word Executive Narrative front layer (§0 "Почему вы получили этот аудит" + 60-second BLUF) and adversarially red-team it
    send: true
---

## User Input

```text
$ARGUMENTS
```

Optional flags:

- `--client <slug>` — company/client directory (writes `clients/<slug>/workaround-audit.md`)
- `--mode <smb | delivery-economics>` — switch between Local SMB (operations/booking) and B2B Services (utilization/invisible work)
- `--async-intake <path/to/intake.json>` — ingest 9-Gate Stage 0 Qualification Packet
- `--payroll-band <range>` — monthly OpEx/Payroll sensitivity band (prevents revenue guessing)
- `--full-dso` — enable Full mode with DSO capital lock (requires receivables & cost of debt)
- Free-form context: observed vacancies, tools, headcount, reported times, stakeholder roles.

ultrathink
> "Главная цель аудитора — не найти засор любой ценой, чтобы продать свой софт, а как можно быстрее убить ложные гипотезы и защитить клиента от ненужных строек. Настоящий цифровой сантехник держит в фокусе Нулевую Гипотезу, проверяет гипотезу здорового роста (Alt 0), режет веру на слово по таблице весов улик и прямо спрашивает себя: 'Посоветовал бы я эту херню, если бы мне запретили продавать её разработку?'" — Valera

## Goal

Generate a client-facing 3–5 page Forensic SpecKit Discovery Diagnostic Memo ($350–$490 Product 0 Tripwire).
Operate strictly as a solo practitioner wearing four explicit hats: **Diagnostic Auditor**, **Forensic Process Analyst**, **Systems Architect**, and **Product Discovery Lead**. Писать строго от первого лица единственного числа (**«я»**, а не «мы»).

Primary Auditor Objective:
**Not to find a bottleneck. To eliminate incorrect bottlenecks as quickly as possible via subtractive epistemology (Via Negativa).**

Key Mandates:

1. **Stakeholder Triad & Owner ≠ Authority Separation (Mandatory Fields):**
   - Identify the **Beneficial Owner** (legal/equity owner in official registries, e.g. 100% shares) vs. the **Budget Authority** (individual with discretionary personal P&L signing authority ≥ $5,000 — CEO, COO, or VP Ops).
   - If `budget_authority_verified` is NOT confirmed (or interviewee is an operational delegate with zero signing power), Product 2 (Build) is strictly **HARD LOCKED**.
2. **Mandatory Telemetry Triage (Principle XVI / ISO 25012 / Zero-GIGO):**
   - **GREEN (Usable L1 Telemetry):** Automated VCS commit logs, CI/CD pipeline runs, APM access traces, immutable deployment webhooks.
     → **Product 2 eligible** (permits full DORA metrics calculation, definitive bottleneck localization, and custom build consideration with projected ROI ≥ 5×).
   - **YELLOW (Incomplete L2/L3 Telemetry):** Jira/YouTrack timesheets with >20% missing estimates or irregular logging.
     → **Product 1 maximum** (enforces mandatory 50% Forensic Haircut + OSINT/Internal weighting W ≤ 0.5; permits indicative friction range modeling only; caps commercial path at Product 1 Governance/SOP).
   - **RED (Toxic Telemetry / Goodhart Collapse):** Chats (Telegram/WhatsApp), unestimated backlog tickets, bulk timesheet logging ("8h every Friday").
     → **`OBSERVABILITY_BLACKOUT`** finding. FORBIDS dollar leakage estimation and ROI calculations. Restricts intervention strictly to Level 1 SOP for telemetry discipline.
3. **Explicit Discovery Failure Modes (`DISCOVERY_FAILURE_MODE`):**
   Classify and document terminal or restrictive audit outcomes:
   - `NO_AUTHORITY`: Economic Buyer refused access or delegate lacks discretionary spending/signing authority ≥ $5,000. Product 2 locked.
   - `NO_TELEMETRY`: Client demands a software solution but categorically refuses access to screen shares, CSVs, or unvarnished workflow review.
   - `TOXIC_TELEMETRY`: Telemetry is contaminated by Goodhart's law, unestimated chats, or bulk logging ("8h every Friday"), triggering `OBSERVABILITY_BLACKOUT`.
   - `HEALTHY_GROWTH_CONFIRMED`: Alt 0 validated; observed friction or hiring burst is a healthy symptom of business expansion and practice scaling, not an operational failure. Verdict: `LEVEL_0_DO_NOTHING`.
   - `CONSTRAINT_DISPROVEN`: Telemetry disproves suspected clog (falsification criteria met; e.g. timesheets show <5% non-billable overhead). Verdict: `LEVEL_0_DO_NOTHING`.
4. **Hard Audit Stop-Loss (Abort Conditions):** Terminate the audit immediately with zero fee capture if any of the following triggers fire:
   - `ABORT_TRIGGER_1: PROXY_INTERVIEW` — Economic Buyer refused access; delegate has zero signing authority.
   - `ABORT_TRIGGER_2: TELEMETRY_BLACKOUT` — Client demands a software solution but categorically refuses access to screen shares, CSVs, or unvarnished workflow review.
   - `ABORT_TRIGGER_3: TOC_DEMAND_GENERATION_COLLAPSE` — Zero inbound pipeline; business has no customers to service.
5. **Commercial Lifecycle & Engineering Traversal Route:**
   Map the commercial lifecycle to engineering intervention levels:

   ```text
   Commercial Route:
   Product 0: Discovery ($350–$490 Tripwire Diagnostic Memo)
     ↓ (requires at least YELLOW telemetry + verified operational friction)
   Product 1: Governance ($1,500–$3,500 SOP/Process Sprint)
     ↓ (HARD LOCKED until GREEN telemetry + proven bottleneck + ROI ≥ 5x + Change Capacity ≥ 4 + Authority Verified)
   Product 2: Build ($5,000+ Sovereign Build Sprint)
   ```

   - Level 0 (Do Nothing) → Outcome of Product 0 if Alt 0 / H₀ holds or failure mode triggers (`HEALTHY_GROWTH_CONFIRMED`, `CONSTRAINT_DISPROVEN`).
   - Level 1 (Process / SOP Change, $0 CAPEX) → Directly feeds **Product 1: Governance Sprint**. Maximum permitted under YELLOW or RED telemetry.
   - Level 2 (Buy COTS SaaS) → Off-the-shelf SaaS configuration / evaluation; no custom build.
   - Level 3 (Deploy Sovereign Bypass / Custom / Template) → Feeds **Product 2: Build Sprint**. Gated by GREEN telemetry + ROI ≥ 5× + verified Budget Authority.
6. **Strict Evidence Weighting Hierarchy (L1–L5):**
   - **Level 1 (W = 1.0):** Primary System Telemetry (server logs, CSV DB exports, git traces, official registry records).
   - **Level 2 (W = 0.9):** Direct Live Observation (15-min live shadowing, recorded work sessions, public engineer resumes/tech artifacts).
   - **Level 3 (W = 0.5):** Internal Statements (verbal interviews, staff time estimates with mandatory 50% haircut).
   - **Level 4 (W = 0.3):** OSINT Signals (open vacancies, ATS postings, public leadership podcasts, association listings).
   - **Level 5 (W = 0.1):** Marketing Material (website copy, vendor PR, award badges).
7. **Forced Uncertainty Declaration (Confidence Ceilings):**
   - Any Confidence >70% strictly requires ≥2 independent evidence sources.
   - Any Confidence >90% strictly requires at least one **Level 1** or **Level 2** artifact.
   - OSINT (L4/L5) alone can NEVER exceed **60% Direction Confidence** and **20% Magnitude Confidence**.
8. **Anti-Heuristic False Precision Ban & Stress-Test Integration:**
   - Explicitly FORBIDDEN to report pseudo-exact dollar figures (e.g. `$9,522/yr`, `$14,318`) on heuristic, verbal, or OSINT data.
   - If L1/L2 primary receipts are missing, exact P&L/leakage modeling is replaced by the **Stress-Test Hypothesis Register** (calibrated ranges + status `ACTIVE / PLAUSIBLE / DORMANT` + declaration of what L1 telemetry unlocks it).
9. **Hypothesis Probability Calibration:**
   - Prohibited to invent pseudo-precise point probabilities (e.g. `P = 47%` or `P = 63%`) without an empirical Bayesian model. Use qualitative epistemic classes: `ACTIVE`, `PLAUSIBLE`, `LIKELY`, `UNCALIBRATED`, `DORMANT`.
10. **Revenue / Headcount Guessing Ban:**
    - Revenue, Headcount, Gross Margin, and Utilization are strictly **`UNKNOWN`** by default. Extrapolations from LinkedIn badges or press releases are banned.
11. **Mandatory Client Health Alternative (Alt 0: Growth & Scaling):**
    - In every competing hypotheses register, the auditor MUST evaluate **Alt 0 (Healthy Expansion / Sustainable Hybrid Model)**: the observed friction, buffer roles, or service-heavy operations are symptoms of healthy business expansion or conscious risk-hedging, not an operational defect.
12. **Cross-Validation Pass (Adversarial Tone Gate):**
    - Mandatory second pass: separate facts from hypotheses and eliminate premature aggression. All early extreme claims (e.g. "scam", "shell company", "broken architecture") that lack direct L1 proof MUST be explicitly documented as retracted or downgraded in the **Cross-Validation Note**.
13. **Domain Asset Engine (Client's Real Moat):**
    - The auditor MUST identify the client's non-replicable asset (regulatory licenses, accreditation networks, specialized BPO audit layer, placement network) before diagnosing software defects. Do not judge a regulatory compliance engine by pure SaaS metrics.
14. **Implementation Conflict-of-Interest Check (The Blindfold Test):**
    - Mandatory query: *"Would I recommend this exact intervention if legally forbidden from selling implementation work (Sprint A / Sprint B / Custom Fork)?"*
15. **Popperian Falsification & Disconfirming Evidence Search:**
    - Mandatory explicit `falsification_criteria` defining what specific telemetry receipt will kill the leading hypothesis.
16. **Pre-Mortem Analysis (Klein Protocol):** Assume failure 6–12 months post-delivery. Detail top 3 failure vectors.
17. **Constraint Relocation Forecast (Goldratt Step 5):** Predict where the bottleneck moves once the primary clog is resolved.
18. **Reversibility Rating (Bezos Type 1 vs. Type 2):** Classify intervention as `HIGH` (Two-Way Door) or `LOW` (One-Way Door).

---

## 0. Output Structure: Two-Layer Memo (MANDATORY)

Финальный артефакт — **двухслойный**. Пишется строго от первого лица («я проверил», «я рекомендую», «я запрещаю»).

### Слой 1 — Executive Narrative (§0, ≤250 слов, ОБЯЗАТЕЛЬНО)

Генерируется командой `speckit.narrative` и валидируется `speckit.red-team-narrative`. Вставляется **в начало** меморандума и дублируется файлом `clients/<slug>/trigger-memo.md`.

Структура §0:

1. **«Почему вы получили этот аудит»** — 1–2 предложения: кто я и по какому поводу пишу. Не называть "Executive Summary".
2. **«Что привлекло внимание»** — 2–3 пронумерованных наблюдаемых сигнала (только факты OSINT/L3, без домыслов о потерях).
3. **«Наиболее вероятное объяснение»** — одна гипотеза с пометкой «предварительная, по открытым данным».
4. **«Альтернативные объяснения»** — минимум одна конкурирующая гипотеза, включая Alt 0 (Healthy Growth / Hybrid Model) или Null Hypothesis.
5. **«Что проверить за 5 дней»** — следующий шаг предельно низкого трения (без продажи софта или спринтов).
6. **«Если у вас есть только 60 секунд»** — BLUF-блок: главный риск; уверенность; какие данные нужны; первый шаг; вероятность того, что нужен новый софт.

### Запреты Narrative-слоя

- ❌ Утверждение диагноза («у вас проблема X») — только «я заметил сигнал X, обычно он связан с A/B/C».
- ❌ Числа потерь без L1/L2 улик (OSINT-потолок: Direction ≤ 60%, Magnitude ≤ 20%).
- ❌ Протечка внутренней кухни: Goldratt, TOC, TDABC, Bayes, Pre-Mortem, Level 0–3 — это язык аудита, не клиента.
- ❌ Продажа решения до завершения диагностики.
- ❌ Объём > 250 слов (счёт по prose-словам, исключая заголовки и идентификаторы).

### Слой 2 — Full Forensic Body (этот документ)

---

## 1. Formal Rubrics, Math & Protocols

### 1.1. TDABC Lite v2 with Calibrated Evidence Weights & Stress-Test Bridge

CoW_Lite = C_FTE + C_SaaS + C_Scrap
where C_FTE = sum(Reported Hours *W_evidence* Loaded Hourly Rate * 52)

- Evidence Weight (W_evidence):
  - `1.0` [Level 1]: Direct server logs, CSV exports, official registry records (GREEN).
  - `0.9` [Level 2]: Observed 15-minute live screen shadowing / recorded dev sessions (YELLOW).
  - `0.5` [Level 3]: Verbal interview claims (*"Takes 30 mins per case"*, mandatory 50% haircut) (YELLOW/RED).
  - `0.3` [Level 4]: OSINT inference (job postings, vacancy requirements) (Direction ≤ 60%, Magnitude ≤ 20%).
  - `0.1` [Level 5]: Marketing claims / website copy.
- **Enforcement Valve:** Если аудит проводится в режиме `outside-in` или действует `OBSERVABILITY_BLACKOUT`, расчет точных потерь в $ ЗАПРЕЩЁН. Вместо псевдоточных формул строится **Stress-Test Hypothesis Register** (§3).

### 1.2. Objective Change Capacity Rubric (1–5 Scale)

| Score | Rating | Objective Behavioral Anchor | Permitted Action |
| :---: | :--- | --- | --- |
| **1** | **Active Rejection** | Previous tool/process abandoned or rolled back within 60 days; staff reverted to shadow channels. | **Level 0 (Do Nothing)** only. Any software burns budget. |
| **2** | **Passive Evasion** | Tool technically active, but >50% of team bypasses it; zero enforcement without owner screaming. | **Level 1 (Executive SOP)** only. Software prohibited. |
| **3** | **Inertial Compliance** | Adoption took 3–6 months; operates with friction; staff complies but complains. | **Level 1 (SOP) or Level 2 (COTS SaaS)** with zero learning curve. |
| **4** | **Managed Adoption** | Dedicated process champion exists; change adopted within 60 days without rollbacks. | **Level 3 (Custom Bypass)** permitted with proven ROI. |
| **5** | **Continuous Kaizen** | Team tests and adopts workflows asynchronously; high digital hygiene; automated telemetry culture. | Full engineering freedom. |

### 1.3. Stage 0 Qualification Packet Protocol (The 9-Gate Intake)

Ingested asynchronously (`--async-intake`) or executed in the first 2 minutes of discovery.

```text
1. [AUTHORITY GATE — OWNER ≠ AUTHORITY SEPARATION]
   - Beneficial Owner (Equity / Official Registry): (a) 100% verified solo founder (b) Multi-shareholder (c) Unverified / OSINT
   - Budget Sign-off Authority (commitments ≥ $5,000): (a) Direct personal sign-off verified (b) Board/Partner consensus required (c) Operational delegate with zero signing power (Locks Product 2) (d) Corporate procurement (Locks Product 2)
   --> If (c) or (d): Lock Product 2 (Build). If Buyer refused access, trigger DISCOVERY_FAILURE_MODE: NO_AUTHORITY.
2. [TOC BOTTLENECK & LEAKY BUCKET GATE] Primary commercial constraint right now:
   (a) Demand Generation: Inbound pipeline dry --> OUT_OF_SCOPE.
   (b) Conversion Leak: Leads lost in chat/delay --> IN_SCOPE (Conversion & Dispatch Plumbing).
   (c) Operational Fulfillment: Overwhelmed delivery/admin --> IN_SCOPE (Fulfillment Plumbing).
3. [CHANGE CAPACITY GATE] Outcome of last tool change in past 12 months: (a) Smooth (4-5) (b) Sabotaged (1-2) (c) Friction (3)
4. [MASTER SYSTEM GATE] Primary system of record (CRM, ERP, or Spreadsheets/Chats).
5. [ARTIFACT READINESS & TELEMETRY TRIAGE GATE (Principle XVI)]
   (a) GREEN (L1 Telemetry): 90-day CSV logs, VCS/CI/CD traces --> W = 1.0. Product 2 eligible.
   (b) YELLOW (Incomplete L2/L3): Live screen share (W = 0.9) or Jira timesheets with >20% missing estimates (W = 0.5 haircut). Product 1 max. Range modeling only.
   (c) RED (Toxic Telemetry): Chats, unestimated backlog, bulk timesheets ("8h Friday") --> OBSERVABILITY_BLACKOUT. Dollar leakage FORBIDDEN. Level 1 SOP only.
6. [HEADCOUNT MULTIPLIER] Core staff involved in friction workflow: (a) 1–5 (b) 6–20 (c) 21–50 (d) 50+. Default: UNKNOWN.
7. [VOLUME RANGE] Monthly volume of core transactions: (a) <50 (b) 50–300 (c) 300–1,500 (d) 1,500+.
8. [ECONOMIC SCALE BAND] Annual revenue / monthly OpEx:
   (a) < $250k/yr ($15–$25/hr loaded) (b) $250k–$1M/yr ($25–$40/hr loaded) (c) $1M–$5M/yr ($40–$75/hr loaded) (d) $5M+/yr ($75–$150/hr loaded). Default: UNKNOWN.
9. [JTBD TRIGGER CATALYST] What specific event in past 90 days forced seeking an audit right now?
```

---

## 2. Output Template (`clients/<client-slug>/workaround-audit.md`)

```markdown
# Forensic Workaround & Margin Leak Audit (Pre-Interview Discovery Memo)

**Client:** [Client Name / Legal Entity / Registration Identifier]  
**Delivery Model:** underundre.com (Solo Productized Engineering Bureau)  
**Date:** [ISO Timestamp]  
**Mode:** [SMB Operational Plumbing | B2B Services Delivery Economics]  
**Status:** PRE-INTERVIEW HYPOTHESIS REGISTER (CALIBRATED / OUTSIDE-IN)  
**Primary Suspected Constraint:** [SUSPECTED_CONSTRAINT_NAME] (UNVERIFIED)

---

## 0. Executive Narrative (§0)

### Почему вы получили этот аудит
[1–2 предложения от первого лица: кто я и по какому поводу провожу скрининг]

### Что привлекло внимание
1. [Наблюдаемый факт OSINT/L1 без интерпретаций]
2. [Наблюдаемый факт вакансий/структуры]
3. [Наблюдаемый факт продуктового позиционирования]

### Наиболее вероятное объяснение
[Одна ведущая гипотеза от первого лица с пометкой «предварительная, по открытым данным»]

### Альтернативные объяснения
- **Alt 0 (Органический рост / Гибридная модель):** [Почему наблюдаемое — нормальная специфика масштабирования или сознательный выбор модели]
- **Alt 5 (H₀ — Нулевая гипотеза):** [Операции стабильны в пределах нормы, вмешательство не требуется]

### Что проверить за 5 дней
[Конкретный шаг минимального трения без продажи софта: запрос 1–2 срезов данных]

### Если у вас есть только 60 секунд (BLUF)
- **Главный риск:** [Формулировка ключевого риска]
- **Уверенность:** [Низкая/Средняя: Direction XX%, Magnitude YY%]
- **Данные для решения:** [Какие конкретно L1 артефакты снимут неопределённость]
- **Первый шаг:** [Калибровочный вопрос или проверка бэклога/P&L]
- **Вероятность того, что нужен новый софт:** [НИЗКАЯ / СРЕДНЯЯ / ВЫСОКАЯ]

---

## 1. Epistemic Horizon & Stakeholder Alignment
- **Beneficial Owner (Legal / Equity):** [Имя, реестр (CA SOS, Companies House, ЕГРЮЛ), статус: VERIFIED | UNVERIFIED]
- **Budget Authority ($5k+ Signing Authority):** [Имя, должность, статус: VERIFIED | DELEGATED | UNVERIFIED]
- **Process Sponsor:** [Имя, операционная роль]
- **JTBD Trigger Catalyst (90-Day Push):** [Событие из Gate 9]
- **Master System of Record:** [Система из Gate 4]
- **Economic Scale Status:** [VERIFIED_FROM_GATE_8: Band X | UNKNOWN (Угадывание запрещено)]
- **Telemetry Quality Triage (Principle XVI):** [GREEN (L1) | YELLOW (L2/L3) | RED (Toxic / Goodhart Collapse)]
- **Observability Status:** [FULL_L1_TELEMETRY | INDICATIVE_FRICTION_RANGE | OBSERVABILITY_BLACKOUT]
- **Discovery Failure Mode:** [NONE | NO_AUTHORITY | NO_TELEMETRY | TOXIC_TELEMETRY | HEALTHY_GROWTH_CONFIRMED | CONSTRAINT_DISPROVEN]
- **Commercial Route Permitted:** [PRODUCT_0_ONLY | PRODUCT_1_GOVERNANCE | PRODUCT_2_BUILD_LOCKED | PRODUCT_2_BUILD_ELIGIBLE]
- **Change Capacity Score (1–5):** [Балл по поведенческому рубрикатору 1.2]
- **Primary Business Bottleneck (Goldratt TOC):** [CONVERSION_PLUMBING / FULFILLMENT / KEY_CUSTOMER_ROADMAP_CONCENTRATION]

---

## 2. Evidence Confidence Register & Hypothesis Tree

### Vacancy Synchrony Analysis
- **Observed Hiring Pattern:** [Анализ кластера вакансий: синхронный наём инженеров vs бэк-офиса]
- **Инженерная / Операционная интерпретация:** [Разбор стека, признаков модернизации vs ручных затычек]

### Cross-Validation Note (Обязательный протокол снятия ранних тезисов)
> *Протокол второго прохода: отделение доказанных фактов от гипотез и устранение необоснованной агрессии.*
> 1. **Тезис [X] СНЯТ:** [Причина снятия, отсутствие L1 доказательств, перевод в статус гипотезы/интерпретации]
> 2. **Тезис [Y] СНЯТ:** [Причина перевода в INSUFFICIENT DATA]

| Наблюдаемый фактор / Сигнал | Направление (Existence) | Масштаб (Magnitude) | Уровень доказательств (L1–L5) | Слепая зона (Требуемые данные L1) |
| :--- | :---: | :---: | :--- | :--- |
| **[Ключевой фактор 1]** | **XX%** | **YY%** | L1: [Источник] + L4: [Источник] | [Что именно нужно запросить] |
| **[Ключевой фактор 2]** | **XX%** | `[UNKNOWN]` | L4: [Источник] | [Что именно нужно запросить] |

*(Уверенность >70% требует ≥2 независимых источников. Уверенность >90% требует L1/L2. OSINT L4/L5 ограничен 60% Direction / 20% Magnitude).*

### Working Competing Hypotheses:
1. **Alt 0 (Healthy Growth / Sustainable Hybrid Model) — [Confidence Class: ACTIVE | PLAUSIBLE | LIKELY | UNCALIBRATED]:** [Наблюдаемое трение — естественный спутник роста или осознанная гибридная сервисная модель].
2. **Alt 1 (Ведущая гипотеза засора) — [Confidence Class: ACTIVE | PLAUSIBLE | LIKELY | UNCALIBRATED]:** [Формулировка основного операционного или структурного дефекта].
3. **Alt 2 (Рыночная диверсификация / Вторичная гипотеза) — [Confidence Class: ...]:** [...]
4. **Alt 5 (Null Hypothesis - H₀) — [Confidence Class: ...]:** [Операции функционируют в рамках допустимой нормы; вмешательство не требуется].

### Popperian Falsification Criteria:
> *Моя ведущая гипотеза ([ИМЯ]) будет полностью ФАЛЬСИФИЦИРОВАНА, если:*  
> **[Конкретный проверяемый факт по первичным данным, который на корню убивает гипотезу].**

---

## 3. Stress-Test Hypothesis Register (Вместо псевдоточных финансов)

> ⚠️ **ПРАВИЛО ЛОЖНОЙ ТОЧНОСТИ:** При отсутствии проверенных L1-выписок (режим Outside-In или Observability Blackout) расчет точных финансовых потерь ЗАПРЕЩЁН. Все финансовые узлы выводятся в виде калиброванных диапазонов с указанием данных, открывающих метрику.

| Метрика / Узел давления | Диапазон / Оценка | Статус | Уверенность | Какие L1-данные открывают метрику |
| :--- | :--- | :--- | :--- | :--- |
| **[Узел 1: Зависимость от ключевого клиента / выручка]** | Диапазон: XX%–YY% | `ACTIVE` | Некалиброванная | Банковские выписки, биллинг-выгрузка |
| **[Узел 2: Сервисная составляющая / ручной труд]** | Диапазон: $Xk–$Yk / yr | `PLAUSIBLE` | Средняя | Акты выполненных работ, номенклатура инвойсов |
| **[Узел 3: Инженерный / Операционный ФОТ]** | Диапазон: $Xk–$Yk / mo | `PLAUSIBLE` | Средняя (L4) | Штатное расписание, ведомости оплат |
| **[Узел 4: Технический долг / Доработка ядра]** | Оценка по спринтам | `ACTIVE` | Средняя (L2) | Git-логи, DORA-метрики, баг-трекер |

---

## 4. Domain Asset Engine Block (Реальный ров компании)

> *Обязательный анализ некопируемого актива клиента: не оценивать предметный бизнес универсальной SaaS-линейкой.*
- **Суть реального актива:** [В чём заключается фундамент доверия и незаменимости: регуляторная аккредитация, партнерская сеть, экспертиза Title IV, BPO-сопровождение audits, наработанная годами репутация?]
- **Защитный барьер от горизонтальных конкурентов:** [Почему универсальные ERP/CRM не могут выбить клиента за один квартал?]
- **Уязвимость актива к внешнему давлению:** [Какие изменения регулятора, законов или ключевых лиц ставят этот ров под угрозу?]

---

## 5. Pre-Mortem & Constraint Relocation Analysis

### 5.1. The Klein Pre-Mortem (Анализ провала через 6–12 месяцев)
*Представим, что предложенное вмешательство полностью провалилось. Топ-3 вектора катастрофы:*
1. **Вектор 1 (Регуляторный / Внешний шок):** [...]
2. **Вектор 2 (Концентрационный / Политический саботаж):** [...]
3. **Вектор 3 (Кадровый / Экспертный дефицит):** [...]

### 5.2. Constraint Relocation Forecast (Goldratt Step 5)
- **Устраняемое ограничение:** [Что именно расшивается].
- **Следующее узкое горлышко:** [Куда немедленно переместится засор].
- **Предохранитель:** [Директива, запрещающая перегрузку нового слабого звена].

---

## 6. The Hierarchy of Interventions & Productization

- **Reversibility Rating:** `[HIGH (Two-Way Door) | LOW (One-Way Door)]`
- **Implementation Blindfold Check:**  
  *Вопрос:* Посоветовал бы я это вмешательство, если бы мне законодательно запретили продавать внедрение?  
  *Ответ:* `[PASS (Непредвзято) | FAIL (Аудит скомпрометирован)]`

### Рекомендации по уровням:
- **Level 0: Do Nothing (Статус-кво):** [РЕКОМЕНДУЮ / ОТКЛОНЕНО]. Условия сохранения текущего режима.
- **Level 1: Process / SOP Change ($0 CAPEX):** [РЕКОМЕНДУЮ / ОТКЛОНЕНО]. Процессная регламентация, разграничение очередей бэклога, SLA.
- **Level 2: Buy COTS SaaS:** [РЕКОМЕНДУЮ / HOLD / ОТКЛОНЕНО]. Готовые инструменты, закрывающие узел без кастомного кода.
- **Level 3: Deploy Sovereign Bypass / Custom Build:** [СТРОГО ЗАПРЕЩАЮ (HARD LOCKED) / ОДОБРЕНО]. Заблокировано до L1-данных и подтверждения полномочий ЛПР.

### 6.1. Productization Opportunities (Product Discovery Lens)
- **Стандартизируемые узлы:** [Какие повторяющиеся процессы можно закрыть типовым регламентом или готовым модулем?]
- **Тиражируемый артефакт:** [Compliance Matrix / Стандартизированный SLA / FOSS-шаблон].
- **Рыночный потенциал:** [Является ли боль системной для всей ниши или уникальна для клиента?]

---

## 7. 🛑 AUTOMATION PROHIBITED LIST (VIA NEGATIVA)
> *Процессы, которые я категорически запрещаю автоматизировать софтом:*
- **[Процесс 1]:** [Причина: высокий регуляторный риск / решается регламентом Level 1 / низкая частотность].
- **[Процесс 2]:** [Причина: риск политического саботажа / зависимость от якорного партнера].

---

## 8. Final Diagnostic Verdict

```yaml
verdict: LEVEL_0_DO_NOTHING | LEVEL_1_PROCESS_SOP | LEVEL_2_BUY_SAAS | LEVEL_3_BUILD_SPRINT | OUT_OF_SCOPE | NO_GO_PRODUCT_0
primary_defect: UNVERIFIED | VERIFIED_CLOG
suspected_primary_constraint: "[NAME_OF_CONSTRAINT]"
beneficial_owner_verified: true | false | UNVERIFIED
budget_authority_verified: true | false | DELEGATED | UNVERIFIED
telemetry_quality: GREEN | YELLOW | RED
data_mode: OUTSIDE-IN | INSIDE-OUT
discovery_failure_mode: NONE | NO_AUTHORITY | NO_TELEMETRY | TOXIC_TELEMETRY | HEALTHY_GROWTH_CONFIRMED | CONSTRAINT_DISPROVEN
commercial_route: PRODUCT_0_ONLY | PRODUCT_1_GOVERNANCE | PRODUCT_2_BUILD_LOCKED | PRODUCT_2_BUILD_ELIGIBLE
null_hypothesis_active: true | false
growth_hypothesis_active: true | false
change_capacity_score: 1-5
economic_buyer_aligned: true | false
blindfold_check: PASS | FAIL
evidence_class:
  - L1_REGISTRY_TELEMETRY: false
  - L2_OBSERVED: true
  - L3_HEURISTIC: false
  - L4_OSINT: true
  - L5_MARKETING: true
reversibility: HIGH | LOW
direction_confidence: XX% (Потолок 60% при L4/L5)
magnitude_confidence: YY% (Потолок 20% без L1)
overall_bayesian_confidence: ZZ%
likely_next_constraint: "[Прогноз следующего узкого места]"
falsification_criteria: "[Критерий опровержения вердикта по первичным данным]"
pre_mortem_top_risk: "[Главный смертельный риск из 5.1]"
recommended_immediate_action: "[Одно конкретное 5-дневное действие без впаривания софта]"
```

---
