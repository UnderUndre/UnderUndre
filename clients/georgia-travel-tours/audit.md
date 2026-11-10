# Mini-Screen: Georgia Travel Tours (Тбилиси, туроп) — Outside-In Hypothesis Register
**Client:** Georgia Travel Tours (georgiatraveltours.ge)
**Delivery Model:** underundre.com | **Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Verdict:** GO (аккуратный заход) | **Питч:** Блок C1 | **Канал:** georgiatraveltours.info@gmail.com / WhatsApp +995 511 199 189, RU

## L2 Артефакты (2026-11-10)
- Vercel + HSTS, HTTPS валиден — стек свежий; НО About = клон главной с заглушками («Travel with us in Europe» ×3, FAQ без ответов), «Popular Tours»/«Discover Georgia» пустые, карта не рендерится, футер на `#`.
- Туры (Сванети, Кхевсурети, Батуми, Имерети) + активности; поиск Where/When/Who есть, онлайн-бронирования/оплаты НЕТ; адрес «Tbilisi, Georgia» без улицы; часы работы не указаны.
- Facebook ~15–18 подписчиков, 0 отзывов; TripAdvisor/Trustpilot/Google Reviews — профиль не найден [IDENTIFIER NOT FOUND].
- LinkedIn: фулстек-инженер Mar–Nov 2025, строил «Next.js 15 + Firebase tour booking platform».

## Hypothesis Register (все UNVERIFIED)
- **H1:** booking-платформу строили, но в прод не выкатили (стек совпадает — Vercel/Next.js, каталог пуст) → заявки в ручном контуре. *L1-признак:* спросить статус платформы и что стоит за формой поиска.
- **H2:** заявки в WhatsApp/почту без CRM → ночные запросы теряются (типовой кейс C1). *L1:* кто и когда отвечает в WhatsApp, есть ли единый реестр заявок.
- **H3:** 0 отзывов + freemail + адрес без улицы → конверсия режется отсутствием соцдоказательства. *L1:* доля вопросов «а вы существуете?» в переписке.

## Персонализация питча
«Поиск на сайте есть, а каталог под ним пустой — заявки уходят в WhatsApp. Так и должно быть, или платформа на пути?» — тон «наблюдение, не приговор» (правило №4 пакета).
