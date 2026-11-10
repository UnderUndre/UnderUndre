# Mini-Screen: Address Boutique Hotel (Тбилиси) — Outside-In Hypothesis Register
**Client:** Address Boutique Hotel (address.com.ge) | **Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Verdict:** GO | **Канал:** sales@address.com.ge (свой домен) | **Питч:** RU/EN, сегмент C3

## L2 Артефакты (2026-11-10)
- EN/KA/RU, HTTPS, © 2026; info@ + sales@ на своём домене. Контент сыроват: часть номеров без описаний, оффер «Price on Online Sources» обрезан.
- Свой /booking/ путь есть, движок не идентифицирован; параллельно — страница GuestReservations (OTA-зависимость подтверждена).
- На сайте messaging «best prices available online from the official website» → rate-parity механика уже осознаётся.
- Репутация: Booking 8.8 (~1440 отзывов), Expedia 9.2, TA активен 2026.

## Hypothesis Register (все UNVERIFIED)
- **H-A:** 15–25% комиссии OTA на заметную долю броней (вилка общеотраслевая, по объекту не подтверждена). *Признак:* тот же номер/дата guestreservations vs site — сравнить цены вечером.
- **H-B:** direct-заявки валятся в info@ без автоматизации. *Признак:* тестовый запрос вечером → замер латентности.

## Персонализация
«Часто за этим стоит владелец-оператор, где менеджер бронирований руками тянет всё — OTA, лояльность и почту».
