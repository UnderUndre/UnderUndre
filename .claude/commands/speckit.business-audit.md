---
description: Perform a forensic business audit, bottleneck diagnosis, and turnaround restructuring plan for an existing business or operating project. Dual-Mode Data Access Gate (--mode inside-out | outside-in): inside-out = full 13-week TWCF direct method (TMA) with bank/ERP L1 data; outside-in = OSINT-only Stress-Test Hypothesis Register with STRICT BAN on precise financial figures. Banned MBA fluff. Focus on 13-week cash runway, As-Is diagnostic (Unit/Contribution margin, aging debt, SIPOC cycle time, Lost-order CustDev), Goldratt TOC bottlenecks, Retrenchment (sanitation/cost cutting), and Renewal/Repositioning roadmap.
handoffs:
  - label: Start Remediation Worktree
    agent: speckit.start
    prompt: Start isolated worktree for fixing the critical operational bottlenecks identified in the audit
  - label: Write Fix Spec
    agent: speckit.specify
    prompt: Write the feature or operational spec to fix the highest-priority bottleneck from the business audit
    send: true
  - label: Audit & Turnaround Review
    agent: speckit.business-audit-review
    prompt: Run an independent forensic review of the business audit and turnaround plan
  - label: Forensic Web Research
    agent: internet-research
    prompt: Run forensic OSINT web research to benchmark turnaround metrics and verify vendor/market ground truth
---

## User Input

```text
$ARGUMENTS
```

Optional args (any order, free text):

- Business / product context, financial statements (P&L, Cash Flow), operational logs, or problem description
- `--create` — force create mode (new comprehensive audit report & turnaround plan)
- `--update` — force update mode (update existing audit after remediation sprint)
- `--path <file>` — explicit audit path (default: auto-detect under `docs/*business-audit*.md` or `docs/*turnaround*.md`)
- `--quick-scan` — emergency triage mode (focus strictly on Phase 0 Cash Flow & Phase 2 Bottleneck)
- `--mode <inside-out | outside-in>` — **MANDATORY Data Access Gate** (default: `outside-in` — safe). `inside-out` = full precision engine, requires L1 artifacts; `outside-in` = OSINT-only Stress-Test Hypothesis Register, precise financial figures FORBIDDEN. See §0 Data Access Gate.
- `--data <glob1,glob2>` — explicit L1 artifact paths (bank statements CSV/XLSX, 1C/ERP export, aging AR register, payment-gateway logs) required for `inside-out`
- `--request-external-review` — after write, print explicit prompt to run `/speckit.business-audit-review` (or manual independent review pass); **auto-on** for CREATE and major pivots

ultrathink

> "Аудит работающего бизнеса — это капиталка старой забитой чугунины прямо в подвале жилого дома под напором кипятка. Пока не нашел течи, не перекрыл аварийные вентили и не сбросил неликвидный шлам — не смей врубать новый насос. Сначала 13-недельный манометр ликвидности, санация костов и расшивка узкого горлышка, и только потом — новый план." — Valera

## Goal

Make the **business audit and turnaround strategy an actionable SpecKit engineering document**, not a theoretical consulting deck:

| Situation                                                 | Mode                                                   | Output                                                                                                 |
| :-------------------------------------------------------- | :----------------------------------------------------- | :----------------------------------------------------------------------------------------------------- |
| **No** `docs/**/*business-audit*.md` (or user `--create`) | **CREATE**                                             | 13-Week Cash Runway + As-Is Forensic Diagnostic + TOC Bottleneck + Retrenchment Plan + Renewal Roadmap |
| Audit exists and this is an iteration (or `--update`)     | **UPDATE**                                             | Same file(s), bump version, log remediation progress, recalculate metrics & updated bottlenecks        |
| Audit exists, remediation in flight                       | **CREATE if empty stub / UPDATE if substantive audit** | Prefer update; never fork silent duplicate audits                                                      |

**When it runs in the pipeline**

1. **Before rebuilding / pivoting an existing business or legacy codebase**: diagnose why current metrics/revenue are leaking before writing any code or spending marketing budget.
2. **When scaling stalls / unit economics degrade**: uncover operational bottlenecks (TOC) and customer churn leaks.
3. **Emergency cash crisis**: triage burn rate, establish a 13-week rolling cash flow, and execute sanitation (Retrenchment).

Does **not** replace `spec.md`. Audit = diagnostic / cash runway / bottleneck analysis / sanitization / pivot strategy; spec = technical implementation of the fix.

## 0. Data Access Gate (Dual-Mode Intake Switch — MANDATORY)

Каждый запуск обязан объявить режим доступа к данным. Это входной редуктор давления: без него команда провоцирует галлюцинации ложной точности — синтетический 13-недельный TWCF и CM₂ по SKU, высосанные из одного URL.

| Mode | Вход (L1-первичка) | Разрешено | СТРОГО ЗАПРЕЩЕНО |
| :--- | :--- | :--- | :--- |
| **`inside-out`** | Банковские выписки за ≥ 90 дней (CSV/XLSX), выгрузка 1C/ERP, закрытые акты, реестр оплат и aging дебиторки, логи платёжного шлюза | Полный движок: боевой 13-недельный TWCF **прямым методом** (TMA standard, допустимая погрешность ≤ 10–15% по ковенантам — не косвенным через EBITDA), CM₂ по SKU, AR aging, PCE/FPY, все пороги §2b | Ничего сверх предоставленного инпута |
| **`outside-in`** | Только OSINT: сайт/лендинг, вакансии, цены, отзывы, стек, соцсигналы | **Stress-Test Hypothesis Register**: каждая метрика — гипотеза с диапазоном и статусом `ACTIVE / PLAUSIBLE / DORMANT` + обязательная колонка «какие данные L1 открывают эту метрику» | **Любые точные финансовые фигуры**: P&L, OCF, Runway в неделях, CM₂ по SKU, AR aging %, пороги §2b как факты |

**Auto-detection:** переданы финансовые файлы/выгрузки → предложить `inside-out`; передан только URL или описание «с улицы» → форс `outside-in` с явным предупреждением. Пользователь переопределяет явно флагом.

**Fail-Safe: Observability Blackout.** Если объявлен `inside-out`, но банковские логи за 90 дней не предоставлены → статус `HEALTHY / STABLE` ЗАПРЕЩЁН; принудительно выставляется `DISCOVERY_FAILURE_MODE: OBSERVABILITY_BLACKOUT`; вердикт ограничивается планом сбора первички (Phase 0 = data collection sprint), инвестиционные рекомендации и вердикты по капиталу запрещены. Это операционализация Принципа XIII (Reality Over Speculation): нет Level 1 — нет точных чисел, есть только гипотезы с диапазонами.

## Core Mindset & Execution Pipeline (The 5-Phase Turnaround Engine)

In an operating business, **value destruction must be stopped before value creation can begin**. The audit MUST follow the canonical turnaround cycle:

```text
[Phase 0: Emergency Liquidity] ──> [Phase 1: As-Is Diagnostic] ──> [Phase 2: Root Cause & TOC]
                                                                             │
[Phase 4: Renewal & Reposition] <── [Phase 3: Retrenchment (Sanitation)] <───┘
```

1. **Phase 0: Emergency Liquidity & 13-Week Cash Forecast (Стоп-кран):** Establish true cash runway. If cash reaches zero in ≤4 weeks, freeze non-essential disbursements, enforce collection of aging receivables, and restructure payables before long-term strategy.
2. **Phase 1: As-Is Forensic Diagnostic (Рентген всей гидравлики):**
   - _Financial_: Separate Cash Flow vs P&L; calculate Contribution Margin by SKU/client; audit Accounts Receivable Aging (0–30, 31–60, 60–90, 90+ days) and Days Inventory Outstanding (DIO).
   - _Process (SIPOC)_: Map Lead-to-Fulfillment cycle time; expose handoff frictions and manual waste.
   - _Customer/Market_: Churn rate, Cohort Retention, and **Lost-Order CustDev** (interviews with churned clients).
3. **Phase 2: Root Cause Analysis & Theory of Constraints (Поиск узкого горлышка):**
   - Apply Goldratt's TOC and the "5 Whys" to separate symptoms (e.g., "sales dropped") from the core bottleneck (e.g., fulfillment delays degrading customer trust and ad conversion).
   - Rule: **Only optimize the bottleneck.** Increasing input before unclogging the bottleneck causes systemic overflow.
4. **Phase 3: Retrenchment & Working Capital Optimization (Санация и сброс балласта):**
   - Kill zombie products/SKUs with negative contribution margins.
   - Liquidate stale inventory to release locked operating cash.
   - Cut non-performing marketing channels and non-essential OPEX.
5. **Phase 4: Renewal & Repositioning Roadmap (Перенаправление и To-Be модель):**
   - Focus 80% of operating power on the high-margin core (Pareto 20%).
   - Score strategic initiatives via ICE / RICE.
   - Define a 2–4 week sprint Roadmap with hard numeric KPI/OKR milestones.

## Operating Constraints

**Writes (allowed paths only):**

- `docs/<product>-business-audit.md` and/or `docs/business-audit.md`
- Multi-brand / multi-unit: `docs/<brand>-business-audit.md`
- Optional: `docs/audits/README.md` index if ≥2 units audited

**Does NOT:**

- Prescribe marketing spend increases when fulfillment/conversion pipelines are leaking
- Confuse revenue with cash on hand (ignoring cash drag and working capital delays)
- Recommend generic corporate restructurings without quantified unit-margin impact
- Hardcode specific proprietary SaaS vendor names (use architectural patterns: cloud billing, unified CRM, pipeline orchestrator)
- Ignore customer churn data in favor of internal executive opinions
- Base industry benchmarks (DSO, DIO, supplier pricing, market alternatives) on unverified memory — MUST ground via `/internet-research` Dorking vectors and Level 1/2 evidence (SEC filings, bankruptcy court records, verified post-mortems). Never rely on Level 3 marketing PR.

## Detection Logic

```text
AUDIT_GLOBS = docs/**/*business-audit*.md , docs/**/*turnaround*.md , docs/business-audit.md
EXISTING_AUDITS = files matching AUDIT_GLOBS

If user --path → AUDIT_PATH = that file
Else if single EXISTING_AUDIT → AUDIT_PATH = it
Else if multiple → ask user which product/brand OR update target specified in args
Else → AUDIT_PATH = docs/business-audit.md (or docs/<slug>-business-audit.md)

If user --create OR (not EXISTING_AUDITS):
  MODE = create
Else if user --update OR EXISTING_AUDITS:
  MODE = update

DATA_MODE:
  If user --mode inside-out AND 90-day bank/ERP/artifact globs present → INSIDE_OUT
  If user --mode inside-out WITHOUT 90-day artifacts → FAILURE_MODE = OBSERVABILITY_BLACKOUT
      (Phase 0 converts to data-collection sprint; HEALTHY/STABLE statuses FORBIDDEN)
  Else (no --mode OR --mode outside-in) → OUTSIDE_IN (default, safe)
      Outside-in FORBIDS: exact P&L/OCF figures, Runway in weeks, CM2 by SKU, AR aging %,
      any §2b threshold emitted as fact → emit Stress-Test Hypothesis Register instead
```

## Execution Steps

### 0. Load inputs

1. Read `$ARGUMENTS` and existing business data: P&L statements, cashflow data, CRM reports, user feedback, `README*`, `docs/*business-plan*` (if any).
2. Load template / standard structure.
3. Identify whether business is in: **Crisis Mode** (runway ≤ 4 weeks), **Stagnation Mode** (bottleneck constraint), or **Pivot Mode** (unit econ broken).

### 1. Mode branch

#### A) CREATE (New Audit & Turnaround Plan)

1. Extract core operational numbers (Revenue, OPEX, Cash runway, Churn, Margin, Cycle Time).
2. Execute **The 5-Phase Turnaround Engine**:
   - **Phase 0:** 13-Week Cash Forecast & Burn Table.
   - **Phase 1:** As-Is Financial Matrix (ABC/XYZ margin, Aging debt, DIO) + Process Cycle Time (SIPOC) + Churn Analysis.
   - **Phase 2:** TOC Bottleneck identification (single primary system constraint).
   - **Phase 3:** Retrenchment Checklist (cut list, zombie SKUs eliminated, working capital liberated).
   - **Phase 4:** Renewal Strategy & Prioritized Roadmap (ICE/RICE scored initiatives).
3. Run **Stress & Forensic Valves Pass** (mandatory).
4. Set version **1.0**.
5. Write `AUDIT_PATH`.
6. Output summary report + next steps (`/speckit.specify` to fix the primary bottleneck).

#### B) UPDATE (Progress & Remediation Check)

1. Read existing audit end-to-end.
2. Diff previous bottlenecks and metrics against newly achieved numbers (cash runway, freed working capital, bottleneck throughput).
3. Update TOC constraint (did the bottleneck move?).
4. Update Retrenchment status and Renewal milestone deliverables.
5. Prepend **Changelog** row with deltas.
6. Re-run **Stress Pass**.
7. Write file.

### 2. Stress & Forensic Valves Pass (Mandatory Turnaround Gates)

Before finalizing, audit against these non-negotiable operational valves:

| Valve                               | Turnaround Requirement                                                                                                                          |
| :---------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Liquidity Reality Check**         | Never assume future accounts receivable will pay on time; apply 20–30% delinquency haircut on 60+ day receivables in the 13-week cash model.    |
| **The Pumping-in-Clog Ban**         | BANNED increasing ad spend if conversion rate is declining due to product defects or fulfillment SLA breaches.                                  |
| **Zombie Product Execution**        | Any SKU/service with negative contribution margin after full variable cost allocation MUST be scheduled for immediate repricing or termination. |
| **Working Capital Release Target**  | Must explicitly quantify cash to be liberated from stale inventory (DIO > 90d) and uncollected invoices (DSO > 45d).                            |
| **BNPL / Installment Haircut (Financing Gate)** | Installment sales through banks/BNPL are NOT plain receivables: `Net_Cash_Realized = Gross_Contract × (1 − MDR) − Provision_for_Churn_Refunds`. Bank MDR discount on installment contracts runs 10–18% taken upfront; when credit term ≫ service term (12-month credit on a 4-month course), book a churn-refund regress provision — bank claws back funds on student drop-off. Counting installments as plain AR inflates cash position and hides the leak. |
| **Founder Extraction / Tax Tunneling Valve** | In turnover-tax jurisdictions (Armenia / CIS, ИП regimes) official EBITDA is meaningless until normalized: owner's personal expenses booked as subcontracts, "consulting fees", or representative costs MUST be reclassified before any margin/runway conclusion. |
| **False Precision Ban (Dual-Mode Enforcement)** | In `outside-in` mode ANY exact financial figure (Runway in weeks, CM₂, AR aging %, OCF) in the output = reject own draft. Emit Stress-Test Hypothesis Register (range + ACTIVE/PLAUSIBLE/DORMANT + "what L1 data unlocks this") instead. In `inside-out` without 90-day artifacts — same ban + OBSERVABILITY_BLACKOUT. |
| **Single Primary Constraint (TOC)** | Exactly ONE primary operational bottleneck must be declared as the active constraint. Declaring 5 equal bottlenecks is prohibited.              |
| **Lost-Order Empirical Proof**      | Churn reasons cannot be based on internal staff opinions; must cite direct feedback from lost customers / churn interviews.                     |
| **Capacity & Key-Person Shield**    | If the primary constraint is founder/key-person operational overload, plan MUST mandate delegation, automation, or scope down-sizing.           |

### 2a. Canonical Strategic Frameworks for Turnaround

Every generated audit MUST incorporate these core methodologies:

1. **Turnaround Management Association (TMA) Stabilization Model:**
   - Strict separation of emergency cash stabilization (Retrenchment) from strategic growth (Renewal).
2. **Theory of Constraints (Eliyahu Goldratt — _The Goal_):**
   - Locate the system's weakest link (Bottleneck). Subordinate all other activities to exploiting and elevating that single constraint.
3. **13-Week Rolling Cash Flow Model:**
   - Weekly cash in/out forecasting to eliminate blind spots and prevent insolvency.
4. **Contribution Margin & ABC/XYZ Matrix:**
   - Sort business lines by gross margin contribution. Isolate the Vital Few (Top 20% margin drivers) from the Trivial Many (80% resource hogs).
5. **Lean Waste Elimination (Muda / DOWNTIME):**
   - Eliminate Defects, Overproduction, Waiting, Non-utilized talent, Transportation, Inventory, Motion, and Extra-processing.
6. **Lost Customer / Churn Forensic Interviewing:**
   - Qualitative discovery on why paying accounts cancel or choose alternatives.
7. **ICE / RICE Initiative Prioritization:**
   - Rank corrective initiatives by $(Impact \times Confidence) / Effort$.

---

### 2b. Advanced Forensic Audit & Turnaround Diagnostic Framework (questions-for-businesses synthesis)

When executing a business audit or turnaround plan, the audit MUST evaluate and encode the **5-Category Forensic Diagnostic Framework** and **Advanced PE/VC Metrics**:

> ⚠️ **Mode Gate:** все пороги и формулы ниже — precision-инструменты режима `inside-out` (L1-первичка на руках). В режиме `outside-in` каждая метрика ОБЯЗАНА выйти в Stress-Test Hypothesis Register: диапазон + статус (`ACTIVE / PLAUSIBLE / DORMANT`) + «какие L1-данные открывают метрику». Точная цифра без первички в outside-in = галлюцинация ложной точности (defect уровня HIGH, см. Quality Bar).

**Канонический формат Stress-Test Hypothesis Register (таблица):**

| Метрика / Гипотеза | Диапазон / Оценка | Статус | Уверенность | Какие L1-данные открывают метрику |
| :--- | :--- | :--- | :--- | :--- |

- Статусы: `ACTIVE` (сигнал горит), `PLAUSIBLE` (согласуется с картиной), `DORMANT` (нет данных). Подтверждённые артефакты помечаются отдельно («Подтверждено, L4»).
- Каждая строка — гипотеза с диапазоном, не факт. Финансовые метрики без L1 = `[INSUFFICIENT DATA]`, не точные цифры.

**Cross-Validation Note (обязательно для outside-in аудиторов):** перед отправкой клиенту прогони второй независимый проход (другая модель или чистая сессия) с установкой «раздели факты и гипотезы, убей категоричность». Все снятые ранние тезисы фиксируются в обязательном блоке **Cross-Validation Note** («утверждение X снято кросс-чеком, потому что Y»). Урок GortsUp: тезисы «массовый отвал», «инфобиз», «кассовый разрыв» были сняты кросс-чеком — и именно этот блок превратил агрессивный документ в заслуживающий доверия. Непроверенная агрессия, отправленная клиенту, = HIGH defect.

#### 1. Liquidity, Runway & Financial Leaks (13-Week Cash Flow & TWCF)

- **Net Liquid Runway:** $\text{Runway} = \frac{\text{Cash \& Cash Equivalents} - \text{Restricted Cash}}{\text{Weekly Net Cash Burn}}$.
  - _Emergency Threshold:_ **< 4 Weeks** → Enforce **Code Red & Cash Czar** protocol (centralized payout control under CFO/turnaround lead, freeze non-essential disbursements).
- **Operating Cash Flow to EBITDA Conversion:** $\text{Ratio} = \frac{\text{Direct Operating Cash Flow}}{\text{EBITDA}}$.
  - _Emergency Threshold:_ **< 0.5** or negative OCF with positive EBITDA → paper profits, uncollected debt, or fake revenue recognition.
- **Cash Conversion Cycle ($CCC$) & AR Aging:** $CCC = \text{DIO} + \text{DSO} - \text{DPO}$.
  - _Emergency Threshold:_ $\text{AR}_{90+} > 15\%$ of receivables → mandatory bad-debt write-off. $CCC > 90$ days → working capital trapped.
- **Installment / BNPL Sales (Financing Gate):** рассрочка через банк/BNPL — НЕ дебиторка: `Net_Cash_Realized = Gross_Contract × (1 − MDR) − Provision_for_Churn_Refunds`.
  - _Thresholds:_ MDR банка на рассрочку 10–18% списывается сразу; при кредите 12 мес на услуге 4 мес — закладывать резерв под регрессные требования банка при оттоке клиента (досрочно расторгли → банк требует возврата средств). Отражать в CCC отдельной строкой, не в plain AR.

#### 2. Profitability & SKU/Client Rationalization (Contribution Margin & ABC/XYZ)

- **Contribution Margin ($CM_1, CM_2$):** $CM_2 = (\text{Revenue} - \text{Direct COGS}) - \text{Direct Variable Selling \& Logistics}$.
  - _Emergency Threshold:_ $CM_2 \le 0$ on any SKU → immediate product delisting or repricing regardless of volume.
- **Founder Extraction / Tax Tunneling Valve:** в юрисдикциях с оборотным налогом (Армения / СНГ, ИП-режимы) официальная EBITDA не значит ничего: личные расходы собственника, проведённые под видом субподрядов, «консалтинговых fees» или представительских, ОБЯЗАНЫ быть реклассифицированы до любых выводов по марже и runway. Ненормализованная EBITDA = фиктивная точка отчёта.
- **Tail SKU Margin Share:** Category C SKUs (bottom 50% volume) giving $<5\%$ margin while locking $>30\%$ inventory and $40\%$ warehouse OPEX → mandatory delisting.
- **Net Customer Margin Post Cost-to-Serve:** Top revenue clients with negative margin post-service costs → immediate contract renegotiation or termination.

#### 3. Bottleneck Identification & Process Flow (TOC & Lean Flow)

- **WIP Accumulation Factor:** $\text{WIP Factor} = \frac{\text{WIP in front of Station}}{\text{Daily Output Capacity of Station}}$.
  - _Emergency Threshold:_ **> 3 days** of work queued in front of a station → primary TOC constraint (Drum-Buffer-Rope violation).
- **Process Cycle Efficiency ($PCE$):** $PCE = \frac{\text{Value-Add Time}}{\text{Total Lead Time}} \times 100\%$.
  - _Emergency Threshold:_ **< 5%** → 95%+ of lead time is non-value-add waiting and queueing (Lean Muda).
- **First Pass Yield ($FPY$):** **< 80%** on critical nodes → 20%+ of operational capacity wasted in rework loops.

#### 4. Churn Forensics & Lost-Customer Analysis

- **Net Revenue Retention ($NRR$):** Threshold **< 85%** B2B Enterprise / **< 95%** Mid-Market → churn exceeds CAC payback period.
- **Operational Churn Ratio ($\text{OpChurn\%}$):** Lost ARR due to delivery/SLA failures **> 30%** → systemic operational defect.
- **Customer Concentration Risk Index:** Single client **> 25%** revenue or Top 3 **> 50%** → extreme concentration risk requiring Ship-or-Pay contracts.

#### 5. Retrenchment & Cost-Cutting Filter (ZBB & Asset Liquidation)

- **Zombie Project Cash Drain Ratio:** Unprofitable R&D/projects burning **> 20%** free cash → immediate project freeze.
- **Dead Stock Working Capital Ratio:** Inventory with no movement $>90$ days **> 25%** → deep discount liquidation to release working capital.
- **Non-Core Overhead Burden Ratio:** Non-essential G&A **> 35%** of OPEX → Zero-Based Budgeting (ZBB) audit.

#### 6. Advanced VC & PE Due Diligence Metrics

- **Burn Multiple:** $\frac{\text{Net Cash Burn}}{\text{Net New ARR}}$. Threshold: **> 3.0x** → unsustainable cash burn.
- **SaaS Magic Number:** $\frac{(\text{Quarterly Rev}_Q - \text{Quarterly Rev}_{Q-1}) \times 4}{\text{S\&M Spend}_{Q-1}}$. Threshold: **< 0.5** → immediate freeze on GTM hiring.
- **Debt Service Coverage Ratio ($DSCR$):** $\frac{\text{EBITDA} - \text{CAPEX} - \text{Taxes}}{\text{Interest} + \text{Principal}}$. Threshold: **< 1.1x** → technical default risk.
- **Maintenance CAPEX vs Depreciation:** $\frac{\text{Maintenance CAPEX}}{\text{D\&A}}$. Threshold: **< 0.5x** → deferred maintenance / fake short-term EBITDA.
- **Bus Factor & Single-Source Supplier Exposure:** Key person single point of failure OR $>30\%$ supply dependency with $>3$ months switching lead time → critical risk.

#### 7. Deep Forensic & Hydraulic Telemetry Valves (Из книги «Сантехника бытия»)

- **WoT Sink-Faucet Macro-Balance:** При наличии внутренней квазивалюты (кредиты, баллы, токены) аудит обязан свести баланс генерации (Faucets) и обязательного утилизационного сжигания (Sinks). Запрещено масштабировать эмиссию без дефляционных затворов (Tier X Repair Drain).
- **Stoll 75-Cent Anomaly Gate:** Расхождение между данными платежного шлюза, CRM и банковской выписки даже на $0.75 запрещено списывать на погрешность округления. Требуется 100% трассировка Root Cause.
- **SCADA Watchdog & Dashboard Staleness:** Запрещено выносить аудиторское заключение по агрегированным BI-дашбордам без проверки свежести сырых логов (Heartbeat SLA <= 15 мин). Зависший дашборд приравнивается к слепоте диспетчеров блэкаута 2003 года.
- **Sleipner A Non-Linear Stress Gate:** Стресс-тест чувствительности финансовой модели обязан рассчитываться в узловых точках максимального сдвигового напряжения (отвал ТОП-1 клиента + задержка дебиторки на 60 дней), а не по усредненным линейным выборкам NASTRAN.

---

#### 8. Domain Asset Engine Block (Client's Real Moat — GortsUp lesson)

Стандартные линзы смотрят на LMS/CRM/сайт/рекламу. Обязательный блок аудита — выявить **настоящий актив клиента**, который не копируется конкурентами, и построить под него отдельную таблицу метрик (вне зависимости от того, куда «принято» смотреть в отрасли).

- Пример (EdTech, кейс GortsUp): компания продаёт не курсы, а гибрид **Education + Recruiting + Employer Network** → блок Career Placement Engine: Employer Partners Count (активные vs витринные) · Placement Rate Verification (методика «79%») · Employer Concentration Risk · Graduate Outcome Tracking · Recruit Event ROI.
- Правило: контент копируется, сотрудники переманиваются, сайты переделываются — доверие работодателей/клиентов нарабатывается годами. Найти этот актив и завести его метрики в Hypothesis Register (статус DORMANT до L1).
- Проверочный вопрос собственнику: «Что из вашего бизнеса конкурент не может скопировать за квартал?»

### 3. Review Policy

Business-audit quality uses **three layers**:

| Layer                             | Who                                                                           | When                                                        | Output                                                      |
| :-------------------------------- | :---------------------------------------------------------------------------- | :---------------------------------------------------------- | :---------------------------------------------------------- |
| **A. Forensic Valves Pass**       | This command (authoring model)                                                | Every CREATE/UPDATE                                         | In-audit stress tables and sanity checks                    |
| **B. Remediation Alignment**      | `/speckit.specify` + `/speckit.review`                                        | Every remediation feature                                   | Verify technical specs address the primary audit bottleneck |
| **C. External Turnaround Review** | Independent provider (Gemini/Grok/Codex) via `/speckit.business-audit-review` | **CREATE** always recommended; **major** pivot MUST request | `docs/reviews/business-audit-<provider>.md`                 |

---

### 4. Completion Report

```text
✓ Business audit [CREATE|UPDATE] vX.Y
  Path:              docs/...
  Data Mode:         INSIDE-OUT | OUTSIDE-IN
  Failure Mode:      NONE | OBSERVABILITY_BLACKOUT
  Cash Runway:       N weeks (Status: CRITICAL | STABLE | HEALTHY)   [inside-out only]
                     UNKNOWN — Stress-Test Hypothesis Register        [outside-in]
  Primary Constraint: [Identified TOC Bottleneck] (hypothesis in outside-in)
  Retrenchment:      [N cost cuts / X working capital liberated]
  Renewal Priority:  [Top 1-2 RICE-scored initiatives]
  External review:   RECOMMENDED | REQUIRED (major)
  Next:              /speckit.specify (target: primary bottleneck) OR /speckit.business-audit-review
```

---

## Quality Bar (Reject Own Draft If)

- Emits precise financial figures (Runway in weeks, CM₂ by SKU, AR aging %, OCF) while in `outside-in` mode — false precision hallucination, reject regardless of narrative quality
- Declares `HEALTHY / STABLE` status while `DISCOVERY_FAILURE_MODE: OBSERVABILITY_BLACKOUT` is active
- Counts bank-installment (BNPL) revenue as plain receivables without MDR haircut (10–18%) and churn-refund regress provision
- Draws margin/runway conclusions from non-normalized EBITDA in turnover-tax jurisdictions (owner extraction not reclassified)
- **Ships outside-in audit without a Cross-Validation Note** (второй проход не прогнан или снятые тезисы не задокументированы)
- **Fails to identify the client's real moat/asset** (Domain Asset Engine Block отсутствует или подменён отраслевым шаблоном)
- Recommends marketing expansion when operational bottlenecks or customer churn are unresolved
- Lacks a concrete 13-week cash runway analysis **in inside-out mode** (in outside-in mode — lacks the Stress-Test Hypothesis Register instead)
- Confuses accounting profit (P&L) with real bank liquidity (Cash Flow)
- Fails to identify a single primary operational bottleneck (TOC)
- Suggests new strategic investments before executing basic sanitation/cost-cutting (Retrenchment)
- Retains negative-margin products/services without explicit repricing/kill criteria
- Lacks direct qualitative voice-of-churn/lost-customer feedback
- Initiatives lack ICE / RICE scoring or explicit milestone metrics

## Coordination

| Command                   | Duty                                                                                                  |
| :------------------------ | :---------------------------------------------------------------------------------------------------- |
| `/speckit.business-audit` | **Author/Update:** Forensic diagnostic, cash triage, bottleneck analysis, retrenchment & renewal plan |
| `/speckit.specify`        | **Execute Fix:** Draft feature/system spec targeting the primary bottleneck identified in the audit   |
| `/speckit.plan`           | **Architect:** Ensure technical architecture removes the operational constraint                       |
| `/speckit.analyze`        | **Audit Drift:** Check if feature specifications solve the audited business defect                    |
