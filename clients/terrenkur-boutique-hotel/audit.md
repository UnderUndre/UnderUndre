# Mini-Screen: Terrenkur Boutique-hotel (Алматы) — Outside-In Hypothesis Register
**Client:** Terrenkur Boutique-hotel (Алматы, Казахстан; Бутик-отель)
**Site:** https://www.terrenkur.kz/pages/about-us | **Контакт:** Email: terrenkur.h@gmail.com; Адрес: пр. Достык, 12868
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.4, строка 7) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Отель на престижном пр. Достык, 128 использует на сайте terrenkur.kz бесплатную почту terrenkur.h@gmail.com68.
- Живость бизнеса: Действующий бутик-отель в районе терренкура Алматы68

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
