# Mini-Screen: Sea Star Boutique Hotel (Алматы) — Outside-In Hypothesis Register
**Client:** Sea Star Boutique Hotel (Алматы, Казахстан; Бутик-отель)
**Site:** https://seastarhotelkz.com/ | **Контакт:** Email: Seastarhotel.kz@gmail.com; Тел.: +7 771 110 00 5869
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.4, строка 8) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Отдел бронирования использует бесплатную почту Seastarhotel.kz@gmail.com вместо доменной почты на @seastarhotelkz.com69.
- Живость бизнеса: Действующий отель в Алматы69

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
