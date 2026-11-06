---
description: Generate a grounded Sales/GTM Plan for UnderUndre (SpecKit Discovery-led outbound) from the business plan, Trigger Playbook, touch log, and delivered audit cases. Enforces epistemic classes on funnel math, Tool Ladder gates, and Duplex delivery channels. Refuses desk-research plans without signal grounding.
handoffs:
  - label: Run Daily Outreach
    agent: speckit.outreach-sdr
    prompt: Execute the daily signal-to-touch loop according to the approved sales plan
    send: true
  - label: Update Business Plan
    agent: speckit.business-plan
    prompt: Reconcile funnel math and GTM spine changes discovered while building the sales plan
    send: false
---

## User Input

```text
$ARGUMENTS
```

Optional flags:
- `--segment <smb-services | b2b-consulting | agencies | all>` — focus segment
- `--period <weeks>` — planning horizon (default: 8 weeks)
- `--refresh-research` — re-run industry benchmark web research (priors only, tagged [HEURISTIC])

ultrathink
> «Маркетинг-план без сырого лога касаний — это фантазия на салфетке. Я строю план от сигналов: где мерещится засор у чужого бизнеса, туда и несём опрессовку. 100 часов кабинетного ресерча стоят меньше одного реального разговора с клиентом.» — Valera

## Grounding Sources (обязательно прочитать перед построением)

1. `undreplans/docs/projects/underundre/business-plan.md` — v20.2b: цены, ICP, Duplex Delivery Protocol, Demand Gate, WIP ≤ 2.
2. `UndeRoute/.specify/templates/trigger-playbook.md` — 13 триггеров, Writing Rules, Red Flags.
3. `undreplans/docs/projects/underundre/outreach-touch-log.md` — L1 конверсии (если есть строки; если нет — все конверсии [HYPOTHESIS]).
4. Доставленные кейсы: `undreplans/docs/projects/underundre/clients/{ermak,aquiva,cal-dot-com}/workaround-audit.md` — реальные Discovery-продукты (для proof-points в офферах).
5. Конституция `undreseller/.specify/memory/constitution.md` — Принципы XIII (WIP), XIV (Signal-Based GTM), XV (Narrative Layer).

## Goal

Generate `undreplans/docs/projects/underundre/sales-plan.md` — операционный маркетинг/сейлз-план аутрича под SpecKit Discovery-воронку. Роль: соло-практик в четырёх шляпах **GTM Strategist**, **Signal Operator (SDR)**, **Funnel Analyst**, **Narrative Editor**.

Жёсткое ограничение: план, который нельзя начать исполнять завтра утром за 2 часа без покупок инструментов, — отклоняется и переписывается.

## 1. Signal Map

Для каждого из 13 триггеров Trigger Playbook:

- **Источник сигнала:** LinkedIn Saved Searches (вакансии), Sales Navigator Job Changes alerts (роли COO/Ops/RevOps/VP Sales — Trigger #13), реестры/новости, hh/DreamJob для CIS-сегмента.
- **Частота мониторинга** и период полураспада сигнала (job change — касание через 3–6 недель; вакансия — пока открыта, свежесть ≤ 7 дней для первого касания).
- **Приоритет p0/p1/p2** — по дешевизне сбора сигнала × ожидаемой концентрации боли (кейс-обоснование: например, Trigger #9 AI Engineer подкреплён кейсом ERMAK).
- Если touch-log уже заполнен — приоритет по доминирующему Reason-коду, а не по вкусу.

## 2. Segments & Channels (Duplex)

- **ICP-срезы под Tripwire $350–$490:** сервисные SMB 3–25 человек (клиники, салоны, property), B2B-услуги/консалтинг (где Founder Bottleneck — кейс ERMAK), агентства (тиражный undreseller path). Гео: ОАЭ/CIS (живые кейсы), затем US/EU (B2B, email-магистраль).
- **Duplex Delivery Protocol (v20.2b):** Email — магистраль (бюджетные решения ≥$5k уходят в почту), Telegram/WhatsApp/LinkedIn — импульсный байпас с селектором предпочтений.
- **Cadence:** 80 ручных LinkedIn + 220 Cold Emails/нед (лимит бизнес-плана), фоллоу-апы по чекпоинтам лога, без автоматизации до закрытия Tool Ladder гейта.
- **Compliance-рамка:** персонализация обязательна, без bulk-бластов и обхода лимитов LinkedIn; в письмах — честный one-click opt-out.

## 3. Offer Ladder (что продаём на каждом рунге)

1. **Рунг 0 — Trigger Note (бесплатно):** сигнал → 2–4 гипотезы → вопрос-выбор сценария. Решение не продаётся.
2. **Рунг 1 — SpecKit Discovery $350–$490 (24–48ч):** TDABC-оцифровка, 4-Level Gate, Trigger Memo (§0 Narrative + 60-сек BLUF). Единственный продукт холодного аутрича.
3. **Рунг 2 — Sprint A $3.5k (FOSS Office) / Sprint B $4.9k (undreseller — default Build path):** только при Level 3 verdict + Change Capacity ≥ 4.
4. **Рунг 3 — Care Retainer $349/мес:** после успешной сдачи.
- Demand Gate: открытие крупных форков ($6.8k+) строго после 10 платных Discovery.
- Каждый рунг содержит явный «что НЕ продаём на этом рунге» (Via Negativa).

## 4. Funnel Math (Epistemic Classes)

Каскад: Sent → Reply → Call → Discovery → Won. Каждая конверсия тегирована:

| Конверсия | Класс | Prior (если лога нет) | Источник |
| :--- | :--- | :--- | :--- |
| Reply rate (generic cold) | [HEURISTIC] | 2–5% | индустриальные бенчмарки `[UNRELIABLE: LEVEL 3]` |
| Reply rate (trigger-based, глубокая персонализация) | [HEURISTIC] | 10–18% | Woodpecker 20M+ писем `[UNRELIABLE: LEVEL 3]` |
| Reply → Call | [HYPOTHESIS] | 30–40% | нет лога |
| Call → Discovery | [HYPOTHESIS] | 25–40% | нет лога (бизнес-план: 28–42% Audit→Sprint) |
| Discovery → Won | [VERIFIED*] | 100% при сдаче (flat-fee эскроу) | при доставленных кейсах |

- Пример расчёта на 300 касаний/нед: при 10% reply → 30 ответов → ~10 звонков → ~3 Discovery/нед → целевые 10 Discovery за ~3–4 недели. Пометка: это [HYPOTHESIS]-сценарий по HEURISTIC-prior; вердикт — только лог.
- **Kill-criteria:** сегмент/канал закрывается, если после 30–50 касаний reply < 5% ИЛИ reply ≥ 15% при Discovery = 0 (крючок острый, гипотеза гнилая — ремонт Possible Hypotheses).

## 5. Operating Rhythm

- **Ежедневно (2–3ч):** 30 мин сбор сигналов (Saved Searches + Job Changes), 90 мин написание Trigger Notes по карточкам пака (Writing Rules обязательны), 30 мин фоллоу-апы по логу.
- **Пятница (1ч):** заполнение touch-log (если не вёл в течение недели — аудита не будет), срез агрегата, фиксация Reason-кодов.
- **Раз в месяц (1ч):** ревизия пака по правилам леджера (30–50 касаний до вердикта), решение по Tool Ladder.
- **WIP:** активных Discovery ≤ 2 параллельно (Принцип XIII); перегруз → Waitlist с депозитом, не аврал.

## Verification

- [ ] План исполняется завтра за 2 часа без новых покупок (Tool Ladder Stage 0)
- [ ] Каждая цифра тегирована эпистемическим классом
- [ ] Offer Ladder не продаёт реализацию до Level 3 verdict
- [ ] Signal Map покрывает все 13 триггеров с указанием источника и decay
- [ ] Kill-criteria сформулированы до запуска, а не после
