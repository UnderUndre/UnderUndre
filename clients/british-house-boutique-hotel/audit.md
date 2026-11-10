# Mini-Screen: British House Boutique Hotel (Тбилиси (Старый город)) — Outside-In Hypothesis Register
**Client:** British House Boutique Hotel (Тбилиси (Старый город), Грузия; Бутик-отель 4 звезды (VIP-сегмент))
**Site:** https://british-house.ge/ | **Контакт:** Email: hotelbritishhouse@gmail.com; Адрес: B. Belinski Str., Tbilisi13
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 14) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Почта на бесплатном домене hotelbritishhouse@gmail.com; нет букинг-движка с онлайн-оплатой — только глухая форма запроса ("Book Request / Reservation possible without a credit card"); интерфейс только на английском (ENG)13.
- Живость бизнеса: Рейтинг 4.9/5 из 481 отзыва (2026 г.); верифицированные отзывы на Expedia/Hotels.com от 5 июля 2026 г. и октября 2025 г.14

## Hypothesis Register
**H1 (UNVERIFIED):** 100% OTA-зависимость → комиссия 15–25% и ноль владения гостем. *проверка:* сравнить direct rate vs OTA на ту же дату.
**H2 (UNVERIFIED):** бронь через gmail → медленный SLA и потеря групповых заявок. *проверка:* тестовый запрос, замер времени ответа.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
