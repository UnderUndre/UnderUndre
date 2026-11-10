# Mini-Screen: Monteva Boutique Hotel (Алматы) — Outside-In Hypothesis Register
**Client:** Monteva Boutique Hotel (Алматы, Казахстан; Бутик-отель)
**Site:** https://montevaboutique.com/en-gb/ | **Контакт:** Email: montevaboutiquehotel@mail.ru; Тел./WhatsApp: +7 707 801 62 673
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.3, строка 19) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: Отдел бронирования использует бесплатную почту montevaboutiquehotel@mail.ru; на англоязычной версии (/en-gb/) слово «микрорайон» (мкр.) переведено машинным переводчиком как «Мистер»: 76 Mr. Gorny Giant str.3.
- Живость бизнеса: Копирайт © MONTEVA BOUTIQUE HOTEL Almaty. 2026; активная карточка в 2ГИС Алматы и каталоге Sonder3

## Hypothesis Register
**H1 (UNVERIFIED):** прямой канал есть, но gmail-бренд и ручные подтверждения съедают конверсию. *проверка:* тестовый запрос, замер SLA.
**H2 (UNVERIFIED):** повторные гости не возвращаются напрямую (нет post-stay базы). *проверка:* есть ли у отеля список прошлых гостей с контактами.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C3/C-отель].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
