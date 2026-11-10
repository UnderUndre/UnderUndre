# Mini-Screen: Palm Tbilisi Boutique Hotel (Тбилиси (Мтацминда)) — Outside-In Hypothesis Register
**Client:** Palm Tbilisi Boutique Hotel (Тбилиси (Мтацминда), Грузия; Бутик-отель 4 звезды)
**Site:** https://palmboutiquehotel.ge/ | **Контакт:** Email: palmhoteltbilisi@gmail.com; Адрес: 3 Alexander Griboedov St 3rd Lane18
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 11) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** HOLD (дефект слабее заявленного) | **Верификация:** VERIFIED-FETCH (2026-11-10): сайт жив, gmail (palmhoteltbilisi@gmail.com) подтверждён; КАПРАВКА: свой booking-движок ЕСТЬ (/booking/, «Best Deal Online» rate-parity) — питч «постройте direct-booking» НЕ РАБОТАЕТ, оффер сужается до бренда-почты и канала повторных гостей.

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Склеенный дубль бесплатной почты palmhoteltbilisi@gmail.com palmhoteltbilisi@gmail.com; 5 карточек номеров продублированы на главной странице 3 раза подряд; противоречие площади в одной фразе (Standard Room – 17 m² This cozy 20 m² Standard room)18.
- Живость бизнеса: Рейтинг 9.0/10 на Booking.com (376 отзывов) и Trivago (99 оценок), 9.2/10 на Trip.com (проверено на даты августа 2026 г.)11

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
