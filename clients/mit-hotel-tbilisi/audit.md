# Mini-Screen: MIT Hotel Tbilisi (Тбилиси (Старый город)) — Outside-In Hypothesis Register
**Client:** MIT Hotel Tbilisi (Тбилиси (Старый город), Грузия; Бутик-отель)
**Site:** https://mithotel.ge/ | **Контакт:** Email: mit.tbilisi@gmail.com; Тел.: +995 505 55 55 16; Адрес: Viktor Jorbenadze St. 2442
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 16) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: На официальном сайте отеля в качестве основного email-контакта указан бесплатный ящик mit.tbilisi@gmail.com42.
- Живость бизнеса: Актуальный официальный сайт с копирайтом © MIT Hotel Tbilisi. 2026, Official site42

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
