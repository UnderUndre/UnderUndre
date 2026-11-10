# Mini-Screen: Mildom City Hotel (Алматы) — Outside-In Hypothesis Register
**Client:** Mildom City Hotel (Алматы, Казахстан; Бутик-отель)
**Site:** https://mildom-city.mildomhotel.com/en-gb/ | **Контакт:** Email: mildom.cityhotel@gmail.com51
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 20) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Сайт нового бутик-отеля размещён на техническом поддомене 3-го уровня (mildom-city.mildomhotel.com), а официальная почта привязана к бесплатному ящику mildom.cityhotel@gmail.com51.
- Живость бизнеса: Актуальный официальный сайт с копирайтом © Mildom City Hotel. 2026, Official site51

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
