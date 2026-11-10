# Mini-Screen: Mukhrantubani Boutique Hotel (Тбилиси (Старый город)) — Outside-In Hypothesis Register
**Client:** Mukhrantubani Boutique Hotel (Тбилиси (Старый город), Грузия; Бутик-отель)
**Site:** https://muhotel.ge/ | **Контакт:** Email: mukhrantubanihotel@gmail.com; Тел.: +995 32 299 74 74; WhatsApp: +995 599 988 00436
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 12) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Корпоративная почта на бесплатном домене mukhrantubanihotel@gmail.com; дублирующийся сырой текст cookie-оверлея (ACCEPT ALL MANAGE COOKIES...) перекрывает контент на главной и странице контактов36.
- Живость бизнеса: Официальный сайт с актуальным копирайтом © Mukhrantubani Boutique Hotel. 202636

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
