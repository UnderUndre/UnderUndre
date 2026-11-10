# Mini-Screen: Bricks Hotel Tbilisi (Тбилиси (Авлабари)) — Outside-In Hypothesis Register
**Client:** Bricks Hotel Tbilisi (Тбилиси (Авлабари), Грузия; Бутик-отель)
**Site:** https://hotelbricks.ge/contacts/ | **Контакт:** Email: bricks.hotel.tbilisi@gmail.com; Тел./WhatsApp/Viber: +995 555 80 98 0941
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 15) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Официальная почта на бесплатном домене bricks.hotel.tbilisi@gmail.com; страница контактов уводит трафик в мессенджеры (WhatsApp/Viber) и QR-код вместо прямого транзакционного модуля41.
- Живость бизнеса: Действующий бутик-отель на 17 Wine Rise (Gvinis Agmarti) в туристическом центре Старого Тбилиси41

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
