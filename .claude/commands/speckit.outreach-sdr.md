---
description: Daily signal-to-touch operating loop for UnderUndre outbound. Harvest fresh signals (vacancies, job changes), match to the 13 Trigger Playbook cards, write Trigger Notes under Writing Rules, log every touch into outreach-touch-log.md. No log entry — no touch counted.
handoffs:
  - label: Write Trigger Memo
    agent: speckit.narrative
    prompt: Build the Trigger Memo for the Discovery lead who replied
    send: false
  - label: Refresh Sales Plan
    agent: speckit.sales-plan
    prompt: Rebuild the plan if the log shows a trigger or channel breakdown
    send: false
---

## User Input

```text
$ARGUMENTS
```

Optional flags:
- `--date <YYYY-MM-DD>` — operating date (default: today)
- `--hours <N>` — timebox (default: 3; полчаса сигналы, 90 мин касания, 30 мин лог)
- `--signal-source <saved-searches | job-changes | registry | all>` — default: all

ultrathink
> «SDR-цикл — это не "написать побольше". Это: поймать свежий сигнал, пока труба не остыла, залить касание по карточке пака, и БЕЗ ЗАПИСИ В ЛОГ — касания не было. Кто ведёт аутрич без лога, тот крутит педали стоя.» — Valera

## Goal

Исполнить один ежедневный цикл signal → touch → log по Trigger Playbook v2.1 и текущему sales-plan. Выход: строки в `undreplans/docs/projects/underundre/outreach-touch-log.md` + подготовленные касания. Всё, что не записано в лог, не существует.

## Daily Loop (жёсткая последовательность)

### Шаг 0. Гигиена контекста (2 мин)

Открыть: Trigger Playbook (карточки + Writing Rules), sales-plan (приоритеты триггеров и сегменты), touch-log (последние строки: какие триггеры уже в работе, какие компании уже тронуты — **дубль касания = инженерный саботаж**).

### Шаг 1. Harvest Signals (30 мин)

По источникам sales-plan Signal Map:
- **Saved Searches (вакансии):** свежие за ≤7 дней по триггерам #1–#8, #10, #12 (hh/DreamJob для CIS, LinkedIn для US/EU).
- **Job Changes (Sales Navigator):** назначения COO/Head of Ops/RevOps/VP Sales за последние 3–6 недель (Trigger #13 — окно изменений).
- **Реестры/новости:** открытия филиалов (#5), миграции платформ (#11).

Каждый сигнал фиксируется с **идентификатором** (ID вакансии, ссылка, дата публикации) — без идентификатора сигнал не существует (Принцип XIV).

Отбраковка мгновенно по Red Flags карточки: сигнал с флагом в мусор, время не тратим.

### Шаг 2. Match → Trigger Card (10 мин)

Для каждого сигнала выбрать карточку триггера. Если сигнал подходит под 2+ триггеров — берём первичный по концентрации боли (кейс-обоснование), вторичный фиксируем в логе как `source` для будущих фоллоу-апов.

### Шаг 3. Write Trigger Notes (90 мин, WIP ≤ 15 за сессию)

По шаблону Copy-Paste Note из карточки, с персонализацией:

1. **Сигнал** — конкретный, с идентификатором («вакансия hh #N от [дата]», «назначение в [компания] от [дата]»).
2. **Гипотезы** — 2–4 сценария из карточки, форма «часто за этим стоит…», НЕ «у вас проблема X».
3. **CTA** — вопрос-выбор сценария (минимальное трение). Решение не продаётся (Принцип XV).
4. **Язык** — по Writing Rules: без цифр потерь, без внутренней терминологии, Alt 0 учитывается. Клиентский текст — стерилен.

Red Flags из карточки = стоп-слово: касание не отправляется, сигнал в архив лога с Reason `BAD_FIT`.

### Шаг 4. Log Every Touch (30 мин, немедленно)

Каждое отправленное касание → строка в touch-log:

```csv
Date,Company,Trigger,Channel,Source,Reply,Call,Discovery,Proposal,Won,Lost,Reason
2026-11-05,Компания N,09-ai-nonai,LinkedIn,vacancy,,,,,,,,,
```

- Чекпоинты пустые до события. Заполнение ≤ 30 сек/строка.
- Ответы на вчерашние касания: проставить `Reply`-дату, при согласии на звонок — `Call`, и сразу handoff в `speckit.narrative` для Trigger Memo.
- Отказы — с Reason-кодом (`NO_PAIN`, `NO_BUDGET`, `NO_AUTHORITY`, `LOST_STATUS_QUO`, `BAD_FIT`…). Отказ без кода = не закрытая строка.

### Шаг 5. Close the Loop (5 мин)

- Счёт дня: сигналов собрано / касаний отправлено / лог обновлён — да/нет.
- Если сессия прошла без заполнения лога — цикл НЕ зачтён. Касаний без строк не бывает.

## Hard Stop Rules (цикл прерывается)

- **Signal drought:** свежих сигналов по p0-триггерам < 3 за 30 мин → не пишем «чтобы было»: пересобираем Saved Searches / проверяем Job Changes window, фиксируем в логе день без касаний (`Reason: NO_SIGNALS`).
- **Reply flood:** пришло 5+ ответов за день → касания стоп, день уходит на Call/Discovery-обработку (это и есть деньги; консервировать воронку ради «плана отправок» — хуйня).
- **Fatigue drift:** после 15 касаний качество персонализации падает → стоп, остальное завтра. Конвейерный шаблонный спам убивает reply rate лучше любого фильтра.

## Verification

- [ ] Каждое касание имеет строку в touch-log (или осознанный `BAD_FIT`-архив)
- [ ] Каждый сигнал — с идентификатором и датой
- [ ] Ни одна заметка не нарушает Writing Rules (гипотезы 2+, без решения, без цифр)
- [ ] Ответы обработаны: Reply/Call проставлены, hot leads переданы в narrative
- [ ] Абонентская дисциплина: никаких новых инструментов не куплено в процессе (Tool Ladder)
