---
description: Generate a public Pattern Teardown (Level 1 of the Public Intelligence Loop) — a generalized mechanism-first breakdown («System Law → example → signal») synthesized ONLY from validated findings. Gated by the Pattern Promotion Gate: ≥3 signals, ≥3 distinct environments, ≥1 survived False Positive. Knowledge product with zero legal risk.
handoffs:
  - label: Ground in Signals
    agent: speckit.signal-teardown
    prompt: Not enough validated findings or distinct environments to pass the gate — build Signal Teardowns from raw signals first
    send: false
  - label: Stage Knowledge Entry
    agent: learn
    prompt: Stage this validated pattern into knowledge/patterns/<slug>.md with status draft for promotion review
---

## User Input

```text
$ARGUMENTS
```

Optional flags:
- `--mechanism <free-form law>` — the System Law headline («Нельзя ускорить разработку, нанимая разработчиков, если горлышко в QA»)
- `--sources <path1,path2,...>` — mandatory grounding: touch-log rows, delivered audits, validated finding notes
- `--format <x | linkedin | blog | all>` — output variants (default: all)

ultrathink
> "Паттерн — это карта, а не местность. Он продаёт не лечение, а осознание симптома. Мозг читателя покупает проблему и механизм, а не разбор чужих вакансий. Но механизм без арматуры —Little, Conway, очередь, Goodhart— превращается в LinkedIn-суп для джунов. Закон системы → наблюдаемое искажение → где интуиция дала сбой. Только так." — Valera

## Goal

Produce a **Pattern / Mechanism Teardown**: публичный разбор обобщённого механизма (System Law), собранный из ≥3 валидированных находок разных контекстов. Читается 3–7 минут. Ноль юридического риска (компаний нет), максимум экспертизы (законы систем — есть).

Это **knowledge product** верхнего уровня Public Intelligence Loop (Principle XIV): строит репутацию «Андрей думает глубже большинства консультантов» и годами приводит читателей в остальную лестницу.

## Pattern Promotion Gate (жёсткий гейт перед написанием)

```yaml
pattern_promotion_gate:
  minimum_signals: 3                      # минимум 3 сырых сигнала
  minimum_distinct_environments: 3        # минимум 3 разные компании/контекста
  minimum_falsification_survivals: 1      # паттерн пережил >= 1 документированный False Positive
  grounding_requirement: "pattern must be grounded in a falsifiable systems mechanism"
```

- **Гейт не пройден →** handoff в `speckit.signal-teardown` (набирать сырьё), паттерн НЕ пишется. Паттерн из пальца — инфоцыганство, запрещено Принципом XIV.
- **grounding_requirement — принцип, не enum:** механизмом считается любая фальсифицируемая системная механика (Little's Law, Conway, Kingman VUT, TOC, Goodhart, Brooks, OODA — и те, что появятся завтра). Хардкод-список фамилий — архитектурный дефект.
- **Механизм обязан быть фальсифицируемым:** в тексте указывается, какое наблюдение опровергло бы закон.

## Структура выхода (канон Mechanism Teardown)

```markdown
# System Law: [одна фраза закона — как заголовок]

## Закон
[Механизм в 1–3 предложениях: почему система ведёт себя именно так. Фальсифицируемо: указано, какое наблюдение опровергло бы.]

## Где интуиция даёт сбой
[Типовое управленческое действие, которое закон делает вредным: «нанимать больше разработчиков при горлышке в QA», «нанимать Tech Writer слишком поздно».]

## Пример из практики (обезличенно)
[1–2 валидированных находки: отраслевой дескриптор + сигнал + чем закончилось. Включая False Positive, если был: «гипотеза не подтвердилась — у них был запуск нового продукта».]

## Как проверить у себя
[1–2 замера, которые читатель сделает за неделю без консультанта.]

## Границы закона
[Где закон НЕ работает: здоровый рост, плановая замена, deliberate risk-control. Это блок честности = блок доверия.]
```

### Форматные варианты (--format)

- **X / Twitter:** тред: закон → пример → граница → вопрос.
- **LinkedIn:** заголовок-механизм («Почему компании нанимают Tech Writer слишком поздно — и почти всегда жалеют»), тело 1200–1800 знаков.
- **Blog:** полная версия с арматурой (Little/Conway/очереди — по-человечески), раздел «Границы закона» развернут, кросс-ссылки на предыдущие teardowns (сеть знаний).

### Render Hygiene (обязательна — артефакт живёт годами в разных вьюверах)

- Ноль `$$`-LaTeX и raw TeX — механики пишутся словами и Unicode (× ≤ ≥ ↔ →).
- Ноль парной денежной записи `$X–$Y` — `X–Y USD`.
- Ноль 2-space вложенных списков — списки топ-левел, подвкладки inline через «;».
- Первое лицо — Андрей (Andrei); «мы» только в цитатах рынка; ноль внутренней кухни (TDABC, номера принципов, Level 0–3).

## Production Rule (Principle XIV — Feed the Pattern)

Паттерн синтезируется СТРОГО из Validated Findings: подтверждённых Discovery ($490), задокументированных False Positive из touch-log, и Signal Teardowns с отслеженным исходом. Производственная последовательность: Raw Signal → Signal Teardown → (3 похожих случая) → Pattern Teardown. Публиковать параллельно можно, производить из воздуха — нельзя.

## Verification

- [ ] Pattern Promotion Gate: 3 сигнала / 3 окружения / ≥1 пережитый False Positive — подтверждено источниками
- [ ] Механизм фальсифицируем: указано опровергающее наблюдение
- [ ] Обезличено: ноль названий компаний (композит или дескриптор)
- [ ] Negative Case включён (если есть в источниках)
- [ ] Рендер-гигиена: без LaTeX/парных $/вложенных списков; Андрей, соло-голос
- [ ] Застейджено в knowledge/patterns/<slug>.md через /learn
