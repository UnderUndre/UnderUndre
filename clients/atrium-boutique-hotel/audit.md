# Mini-Screen: Atrium Boutique Hotel (Тбилиси) — Outside-In Hypothesis Register
**Client:** Atrium Boutique Hotel (Тбилиси, Грузия; Бутик-отель)
**Site:** https://atriumtbilisi.com/ | **Контакт:** Email: info.hotelatrium@gmail.com; Адрес: 54 Nino Chkheidze St, Tbilisi38
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 13) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Почта на бесплатном домене info.hotelatrium@gmail.com; дублирование карточек номеров (Standard Double or Twin Room with view) дважды подряд на главной; текст «Об отеле» скопирован из описания Booking.com в 3-м лице38.
- Живость бизнеса: Активно оперирующий бутик-отель в историческом центре Тбилиси38

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
