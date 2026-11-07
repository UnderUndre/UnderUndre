---
description: Generate a public Signal Teardown (Level 2 of the Public Intelligence Loop) — a 2–5 minute read that breaks down a real market signal into competing hypotheses WITHOUT naming the company. Blinded by default. This is the audience product between Pattern Teardown (knowledge) and Discovery ($490, sales).
handoffs:
  - label: Promote to Pattern
    agent: speckit.pattern-teardown
    prompt: Check whether this finding and 2+ sibling signals have passed the Pattern Promotion Gate, and if so synthesize a Pattern Teardown
    send: false
  - label: Offer Discovery
    agent: speckit.speckit-discovery
    prompt: A reader from this teardown responded with their own situation — build the private two-layer Discovery memo
    send: false
---

## User Input

```text
$ARGUMENTS
```

Optional flags:
- `--source <touch-log | vacancy-id | audit-path>` — the raw signal grounding (MANDATORY per Principle XIV: a teardown without a real signal is synthetic noise)
- `--named-target <company>` — DISABLES anonymization; allowed ONLY if the target has verifiable public status (public company, open-source repo, or written consent). Default: blinded.
- `--format <x | linkedin | blog | all>` — output variants (default: all)

ultrathink
> "Signal Teardown — это не урезанный Discovery. Это другой продукт с другой задачей: не продать аудит, а заставить читателя сказать «этот Андрей реально думает глубже большинства консультантов». Читатель покупает проблему, а не процесс. И если в разборе нет версии «а может у них всё нормально» — это не диагностика, это наезд обиженного аутсорсера." — Valera

## Goal

Produce a public-facing teardown of ONE real signal: **1 проблема → 3 сигнала → 2–4 гипотезы → слепые зоны → 1 следующий шаг**. Reading time 2–5 minutes. Not 5 pages.

This is the **audience product** of the Public Intelligence Loop (Principle XIV): it proves that the bureau's patterns are observed on the real market, feeds the audience layer, and quietly builds the bridge to Discovery ($490) — without ever selling it in the text.

## Санитарные вентили (нарушение любого = публикация запрещена, Принцип XIV)

1. **Blinded by Default.** Целевая компания заменяется отраслевым дескриптором («сервис краткосрочной аренды на 30+ объектов», «B2B SaaS на ~40 человек, стек .NET/React»). Название, домен, город-одиночка, лицензионные номера — запрещены. Флаг `--named-target` разрешает имя только при верифицируемом публичном статусе таргета.
2. **Формулировка сильнее дисклеймера.** Никогда «у компании X проблемы» — всегда «по открытым сигналам можно выдвинуть несколько гипотез». Диагноз = деликтный риск (диффамация); разбор сигналов = protected opinion по раскрытым фактам (Milkovich v. Lorain Journal Co., 497 U.S. 1 (1990); Restatement (Second) of Torts § 566).
3. **Alt 0 Balance.** Не менее 50% объёма гипотез — версии здорового масштабирования и «может, им вообще ничего не нужно». Пост без нулевой версии = токсичный наезд.
4. **Banned Internal Kitchen.** В аутпуте запрещены: TDABC, Goldratt, TOC, Muda, DORA-акронимы без расшифровки, номера принципов конституции, Level 0–3, Change Capacity, W-веса. Только наблюдаемые факты и человеческий язык.
5. **Negative Case.** Если по этому сигналу гипотеза уже опровергалась (False Positive в touch-log) — разобрать публично: «я предполагал X, проверка показала Alt 0». Отрицательный кейс продаёт доверие лучше двадцати победных разборов.

## Структура выхода (канон, 5 блоков)

```markdown
# Signal Teardown: [обезличенный дескриптор ситуации]

## Что увидел
[Только наблюдаемые сигналы: 2–4 факта с источником («вакансии A, B, C открыты одновременно», «роль появилась и исчезла»). Ноль причин, ноль цифр потерь.]

## Возможные объяснения
- **Версия А:** [рабочая гипотеза]
- **Версия Б:** [конкурирующая гипотеза]
- **Версия В (здоровый рост):** [Alt 0 — а может, у них всё нормально]
- *(если был)* **Нулевая:** [проверка покажет, что вмешательство не нужно]

## Чего я не знаю
[Явный список слепых зон: какие данные закрыли бы спор. Это блок честности — его отсутствие выдаёт продавца.]

## Что проверил бы за 1 неделю
[Один конкретный замер/данные. Не продажа решения.]

## Если бы это был мой бизнес
[Один конкретный шаг низкого трения. Тон: «действуй осторожно, сначала измерь».]
```

### Форматные варианты (--format)

- **X / Twitter:** тред 5–8 твитов; хук = парадокс сигнала; последний твит — вопрос аудитории.
- **LinkedIn:** 1200–1800 знаков, тот же скелет; CTA — вопрос, не ссылка.
- **Blog:** полная версия + раздел «Чего я не знаю» развернут; ссылка на услуги допустима один раз в подвале.

### Render Hygiene (клиентский артефакт обязан выжить в любом вьювере)

- Ноль `$$`-LaTeX и raw TeX — только Unicode: × ≤ ≥ ↔ → H₀.
- Ноль парной денежной записи `$X–$Y` — пишем `X–Y USD` / `AED`.
- Ноль 2-space вложенных списков — все списки топ-левел, подвкладки через «;» inline.
- Первое лицо — Андрей (Andrei), founder of underundre.com; никакой «мы» и никакого Валеры в тексте.

## Production Rule (Principle XIV)

Signal Teardown обязан питаться сырым сигналом: `--source` указывает на строку touch-log, ID вакансии или путь к аудиту. Нет источника — нет тирдауна (синтетический «разбор из головы» = инфоцыганство, запрещено Принципом XIV). При 3+ сигналах одного паттерна — handoff в `speckit.pattern-teardown` на гейт-проверку.

## Verification

- [ ] Компания обезличена (или --named-target обоснован публичным статусом)
- [ ] ≥ 50% объёма гипотез — Alt 0 / здоровые версии
- [ ] Нет диагнозов, нет цифр потерь, нет внутренней кухни
- [ ] Есть блок «Чего я не знаю» и один замер за неделю
- [ ] Рендер-гигиена: без LaTeX, парных $, вложенных списков; Андрей, соло-голос
- [ ] Источник сигнала зафиксирован (touch-log строка / ID вакансии)
