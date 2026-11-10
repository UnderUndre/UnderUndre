# Mini-Screen: Route Hotel Tbilisi (Тбилиси) — Outside-In Hypothesis Register
**Client:** Route Hotel Tbilisi (Тбилиси, Грузия; Отель)
**Site:** https://routehoteltbilisi.com/ | **Контакт:** Email: routehoteltbilisi@gmail.com; Тел./WhatsApp/TG: +995 599 60 71 8167
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.4, строка 6) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Отсутствует букинг-движок — сайт предлагает звонить в отдел бронирования или писать на бесплатную почту routehoteltbilisi@gmail.com67.
- Живость бизнеса: Действующий отель на Rustavi Hwy, 467

## Hypothesis Register
**H1 (UNVERIFIED):** 100% OTA-зависимость → комиссия 15–25% и ноль владения гостем. *проверка:* сравнить direct rate vs OTA на ту же дату.
**H2 (UNVERIFIED):** бронь через gmail → медленный SLA и потеря групповых заявок. *проверка:* тестовый запрос, замер времени ответа.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
