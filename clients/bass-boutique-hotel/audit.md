# Mini-Screen: Bass Boutique Hotel (Ереван (Айгедзор)) — Outside-In Hypothesis Register
**Client:** Bass Boutique Hotel (Ереван (Айгедзор), Армения; Бутик-отель 4 звезды (41 номер, винный погреб Maran))
**Site:** https://www.basshotel.am/ru | **Контакт:** Email: bassboutiquehotel@gmail.com; Тел.: +374 10 221353, +374 43 26 10 8046
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 18) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Почта на бесплатном домене bassboutiquehotel@gmail.com; раскол веб\-зеркал между старым http://www.bass.am/eng/ и basshotel.am/ru; нет онлайн-букинга (глухая кнопка «Отправить»)46.
- Живость бизнеса: Действующий 4-звёздочный отель в дипломатическом районе Айгедзор (ул. Айгедзор, 3/1), база размещения международных конференций47

## Hypothesis Register
**H1 (UNVERIFIED):** 100% OTA-зависимость → комиссия 15–25% и ноль владения гостем. *проверка:* сравнить direct rate vs OTA на ту же дату.
**H2 (UNVERIFIED):** бронь через gmail → медленный SLA и потеря групповых заявок. *проверка:* тестовый запрос, замер времени ответа.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
