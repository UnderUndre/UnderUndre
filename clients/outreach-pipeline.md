# 📮 Outreach Pipeline — трекер исходящих касаний (pre-send)

**Назначение:** вести, **кому отослано и кому надо отослать**. Это ПЕРЕД-ответная сторона воронки. После ответа клиента строка уходит в [`touch-log.md`](./touch-log.md) (единственный L1-журнал по Trigger Playbook v2.1) — пайплайн фиксирует исходящий поток и follow-ups до ответа.
**Правила:**
1. Одна строка = один лид = одна активная переписка. Фоллоу-ап тому же лиду — НЕ новая строка (обновляется `FU due`/`FU sent`).
2. Статусы: `QUEUED` (письмо готово/шаблон выбран) → `SENT` (дата) → `FU-DUE` (5 раб. дней без ответа) → `FU-SENT` → `REPLIED` (→ строка в touch-log, дальше живёт там) / `LOST` (Reason-код) / `HOLD` (не слать, причина) / `SKIPPED`.
3. Письмо берётся из [`outreach-message-pack.md`](../../../undreplans/docs/projects/underundre/content/2026-11-10-outreach-message-pack.md) (Блоки A–G) или сегментного шаблона; персонализация обязательна.
4. Перед отправкой из внешних реестров: проверить живость ссылки (реестр Funnel Audit от 10.11.2026 уже показал: 1 из 4 спот-чек ссылок — 410 за сутки).
5. Масс-статусы правятся одной правкой таблицы; история — в git.

---

## Wave 0 — Исторические отказы (уже в touch-log, справочно)

| Lead | Статус | Touch-log строка |
|---|---|---|
| Smart IT Power (Ереван) | LOST | 2026-11-07, LOST_STATUS_QUO |
| Profitov.Partners (Тбилиси) | LOST | 2026-11-09, LOST_STATUS_QUO |
| Employcity (Москва) | LOST | 2026-11-09, LOST_STATUS_QUO |
| SMPower | LOST | 2026-11-07 (см. touch-log) |

---

## Wave 1 — Готовая очередь (аудиты и письма уже собраны, 10.11)

| # | Lead (slug) | Сегмент | Контакт | Письмо | Статус | Sent | FU due | Примечание |
|---|---|---|---|---|---|---|---|---|
| 1 | sofmar | логистика (GE) | elena@sofmar.ge / WA | F1 | QUEUED | | | GO; партнёрство APM Terminals |
| 2 | georgia-travel-tours | турфирма (GE) | gmail / WA +995 511 199 189 | F2 | QUEUED | | | GO; каталог пустой при живом стеке |
| 3 | kamancha | ресторан (AM) | kamancharest@gmail.com | F3 | QUEUED | | | GO ⭐; топ-4 TA без онлайн-брони |
| 4 | kasa-gyumri | гестхаус (AM) | bnb@kasa.am | F4 | QUEUED | | | GO; 100% OTA |
| 5 | dolmama | ресторан (AM) | dolmama98@gmail.com | F5 | HOLD | | | Бронь уже есть; заходить после первых откликов |
| 6 | nicosia-dental | клиника (CY) | info@nicosiadentalclinic.com | F6 | QUEUED | | | GO; EN письмо |
| 7 | elpis-medical | клиника (CY) | administration@elpismedicalcentre.com | F7 | QUEUED | | | GO; staging-хвосты найдены |
| 8 | garant-logistics | фрахт (AM) | WA +374 44 203939 | F8 | QUEUED | | | GO; FIATA перепроверить |
| 9 | kairos | логистика (GE) | info@kairos.ge | F9 | QUEUED | | | GO; фаза роста (Poti 28k м²) |
| 10 | address-boutique-hotel | отель (GE) | sales@address.com.ge | F10 | QUEUED | | | GO; rate-parity осознан |
| 11 | mov-restaurant | ресторан (AM) | info@movrestaurant.com | сегм. C2 ⭐ | QUEUED | | | GO ⭐⭐; кнопка брони → демо-сайт темы; The Times 2026 |
| 12 | georgia-tours | турфирма (GE) | tours@georgia-tours.eu | сегм. C1 | QUEUED | | | GO; Trustindex-отзывы курируются |
| 13 | yiannikos | клиника (CY) | тел/WhatsApp 70070075 | сегм. C5 | QUEUED | | | GO; email не публикуется — начать с WA |
| 14 | infident | клиника (CY) | info@infidentclinic.com | сегм. C5 | QUEUED | | | GO; WHOIS/Wayback докрутить |
| 15 | georgia-trip | adventure (GE) | info@georgia-trip.com | сегм. C1 | QUEUED | | | GO; чешские связи |
| 16 | georgia-adventure-club | B2B-DMC (GE) | info@georgiaadventureclub.com | сегм. C1-B2B | QUEUED | | | GO; телефоны разошлись — сверить |
| 17 | berq-studio | e-com (AM) | Contact Us форма | сегм. C-eCom | QUEUED | | | GO; платежки не видно |
| 18 | MLVentures (Botan/ChaChat) | вакансия Product Analyst | рекрутер | B1 | QUEUED | | | EN; memo приложить |
| 19 | european-village | девелопер (GE) | форма сайта | B2 | QUEUED | | | RU |
| 20 | see-inside | вакансия Assistant CEO | отклик | B3 | QUEUED | | | RU |
| 21 | STARTRIBE LTD | SSC (CY) | LinkedIn/email | B4 | QUEUED | | | EN |
| 22 | EPAM Yerevan | вакансия Sr DevOps | careers.epam.com | D1 | QUEUED | | | отклик на вакансию |
| 23 | Exness Limassol | вакансия Backend/Golang | exness-careers.com | D2 | QUEUED | | | релокация семьи; JS-портал — проверить руками |
| 24 | SoftConstruct | вакансия IT Support | info@softconstruct.com | G1 | QUEUED | | | AM; 176 ролей |
| 25 | BostonGene (via Repat) | вакансия Sr IT Support | repatarmenia.org | G2 | QUEUED | | | ⏰ дедлайн 12.11.2026 — приоритет дня |

---

## Wave 2 — Funnel Audit batch (реестр «B2B Funnel Audit Outside Russia» от 10.11.2026, 41 lead)

Формат: все QUEUED, письма = сегментные шаблоны (стоматологии/клиники → C5/C-клиника; отели → C3; ВЭД/логистика → C4). Верификация в шапке каждого `audit.md` (3 VERIFIED-FETCH, остальные UNVERIFIED: LEVEL 3 до фетча). Приоритет первой десятки — по жирности дефекта и чеку.

| # | Lead (slug) | Город | Ниша | Контакт (первичный) | Статус | Sent | FU due | Примечание |
|---|---|---|---|---|---|---|---|
| dentinn | Dentinn | Тбилиси | Стоматологическая клиника | Email: shotaruxadze999@gmail.com | QUEUED | | | 11.11–14.11 |
| kiknadze-s-dental-center | Kiknadze's Dental Center | Тбилиси (Исани) | Стоматология и челюстно-лицевая хирургия | Email: kiknadzedentalcenter@gmail.com | QUEUED | | | 11.11–14.11 |
| dentor-ia-osadze-dental-clinic | Dentor (Ia Osadze Dental Clinic) | Тбилиси (Сабуртало) | Имплантология и протезирование | Email: dentorclinic@gmail.com | QUEUED | | | 11.11–14.11 |
| llc-astra-dental-clinic | LLC "Astra Dental Clinic" | Тбилиси | Стоматология и имплантология (All-on-4/6 | Email: astradentalclinicgeorgia@gmail.com | QUEUED | | | 11.11–14.11 |
| m-clinic-maria-chelidze-dental-center | M Clinic (Maria Chelidze Dental Center) | Тбилиси (Сабуртало) | Стоматологическая клиника | Email: Mclinicgeorgia@gmail.com | QUEUED | | | 11.11–14.11 |
| buchodenti | BuchoDenti | Тбилиси | Имплантология, виниры E.max, 3D-диагност | Email: iza.dzidzikashvili@gmail.com | QUEUED | | | 11.11–14.11 |
| dental-stomus | Dental Stomus | Тбилиси (Ваке) | Эстетическая стоматология и элайнеры Inv | Email: clinicstomus@gmail.com | QUEUED | | | 11.11–14.11 |
| sas-aesthetica-clinic | SAS Aesthetica Clinic | Дубай (Al Garhoud) | Центр эстетической медицины и антиэйдж-т | Email: sasaestheticaclinic@gmail.com | QUEUED | | | 11.11–14.11 |
| visage-polyclinic-l-l-c | Visage Polyclinic L.L.C. | Дубай (Business Bay) | Эстетическая медицина, дерматология и по | Email: visagepolyclinicllc@gmail.com | QUEUED | | | 11.11–14.11 |
| solar-medical-clinic-l-l-c | SOLAR Medical Clinic L.L.C. | Дубай (Sobha Hartland) | Клиника эстетической медицины (SMAS, ULF | Email: solar.clinic.ae@gmail.com | QUEUED | | | 11.11–14.11 |
| palm-tbilisi-boutique-hotel | Palm Tbilisi Boutique Hotel | Тбилиси (Мтацминда) | Бутик-отель 4 звезды | Email: palmhoteltbilisi@gmail.com | QUEUED | | | 11.11–14.11 |
| mukhrantubani-boutique-hotel | Mukhrantubani Boutique Hotel | Тбилиси (Старый город) | Бутик-отель | Email: mukhrantubanihotel@gmail.com | QUEUED | | | 11.11–14.11 |
| atrium-boutique-hotel | Atrium Boutique Hotel | Тбилиси | Бутик-отель | Email: info.hotelatrium@gmail.com | QUEUED | | | 11.11–14.11 |
| british-house-boutique-hotel | British House Boutique Hotel | Тбилиси (Старый город) | Бутик-отель 4 звезды (VIP-сегмент) | Email: hotelbritishhouse@gmail.com | QUEUED | | | 11.11–14.11 |
| bricks-hotel-tbilisi | Bricks Hotel Tbilisi | Тбилиси (Авлабари) | Бутик-отель | Email: bricks.hotel.tbilisi@gmail.com | QUEUED | | | 11.11–14.11 |
| mit-hotel-tbilisi | MIT Hotel Tbilisi | Тбилиси (Старый город) | Бутик-отель | Email: mit.tbilisi@gmail.com | QUEUED | | | 11.11–14.11 |
| yerevan-boutique-hotel-yb | Yerevan Boutique Hotel (YB) | Ереван | Бутик-отель (винный погреб и ресторан) | Email: yerevanboutiquehotel@gmail.com | QUEUED | | | 11.11–14.11 |
| bass-boutique-hotel | Bass Boutique Hotel | Ереван (Айгедзор) | Бутик-отель 4 звезды (41 номер, винный п | Email: bassboutiquehotel@gmail.com | QUEUED | | | 11.11–14.11 |
| monteva-boutique-hotel | Monteva Boutique Hotel | Алматы | Бутик-отель | Email: montevaboutiquehotel@mail.ru | QUEUED | | | 11.11–14.11 |
| mildom-city-hotel | Mildom City Hotel | Алматы | Бутик-отель | Email: mildom.cityhotel@gmail.com51 | QUEUED | | | 11.11–14.11 |
| tnt-customs | TNT Customs | Алматы | Таможенный брокер и ВЭД | Email: tntcustomskz@gmail.com | QUEUED | | | 11.11–14.11 |
| mlg | MLG (ТПК Алматы) | Алматы | Таможенное оформление грузов (B2B) | Email: tpk.almaty@gmail.com | QUEUED | | | 11.11–14.11 |
| antares | Antares (Антарес) | Ташкент | Таможенный брокер и декларирование | Email: antares.ag@mail.ru | QUEUED | | | 11.11–14.11 |
| asia-brokers-abg-service | Asia Brokers (ABG Service) | Ташкент | Таможенный брокер и B2B-декларант | Email: abgserviceuz@gmail.com | QUEUED | | | 11.11–14.11 |
| great-5-star-plus-g5sp | Great 5 Star Plus (G5SP) | Ташкентская обл. | Таможенный брокер и оформление грузов | Email: great5starplus@gmail.com | QUEUED | | | 11.11–14.11 |
| cargo-handling-kg | Cargo Handling KG | Бишкек | Экспедирование и грузовая обработка | Email: cargohandlingkg@gmail.com | QUEUED | | | 11.11–14.11 |
| garant-trans-logistic | Garant Trans Logistic | Бишкек | Международные грузоперевозки и экспедиро | Email: garant.trans.logistic@gmail.com | QUEUED | | | 11.11–14.11 |
| lincon | LINCON | Бишкек | Таможенный представитель и доставка из К | Email: companylincon@gmail.com | QUEUED | | | 11.11–14.11 |
| mount-rich-shipping-llc | Mount Rich Shipping LLC | Дубай (Al Quoz) | Таможенный брокер и международное экспед | Email: mountrichshipping@gmail.com | QUEUED | | | 11.11–14.11 |
| persona-dental-clinic | Persona Dental Clinic | Тбилиси | Стоматологическая клиника | Email: personadentalgeorgia@gmail.com | QUEUED | | | 11.11–14.11 |
| harley-street-clinic-dubai | Harley Street Clinic Dubai | Дубай | Пластическая хирургия и эстетическая мед | Email: harleystpolyclinic2025@gmail.com | QUEUED | | | 11.11–14.11 |
| berkana-aesthetic-clinic-l-l-c | Berkana Aesthetic Clinic L.L.C. | Дубай | Эстетическая медицина | Email: aesthetics.berkana@gmail.com | QUEUED | | | 11.11–14.11 |
| cure-aesthetic-dental-clinic | Cure Aesthetic Dental Clinic | Дубай | Эстетическая стоматология | Email: alsaffarak@gmail.com | QUEUED | | | 11.11–14.11 |
| royal-core-aesthetic-clinic-l-l-c | Royal Core Aesthetic Clinic L.L.C. | Дубай | Эстетическая медицина и косметология | Тел.: +971 50 849 5990, +971 4 557 254066 | QUEUED | | | 11.11–14.11 |
| route-hotel-tbilisi | Route Hotel Tbilisi | Тбилиси | Отель | Email: routehoteltbilisi@gmail.com | QUEUED | | | 11.11–14.11 |
| terrenkur-boutique-hotel | Terrenkur Boutique-hotel | Алматы | Бутик-отель | Email: terrenkur.h@gmail.com | QUEUED | | | 11.11–14.11 |
| sea-star-boutique-hotel | Sea Star Boutique Hotel | Алматы | Бутик-отель | Email: Seastarhotel.kz@gmail.com | QUEUED | | | 11.11–14.11 |
| gold-boutique-hotel | Gold Boutique Hotel | Алматы | Бутик-отель | Email: gold\_hotel20@mail.ru | QUEUED | | | 11.11–14.11 |
| tms-shipping-and-clearance-l-l-c | TMS Shipping and Clearance L.L.C. | Дубай | Экспедирование и таможня | Email: tms.shippingandclearance@gmail.com | QUEUED | | | 11.11–14.11 |
| solvex | Solvex | Варшава | Экспедирование грузов | Email: solvex@07@gmail.com | QUEUED | | | 11.11–14.11 |
| worldgran-logistics | Worldgran Logistics | Варшава | Транспорт и экспедиция | Email: worldgranlogistics@gmail.com | QUEUED | | | 11.11–14.11 |

**Порядок первой десятки Wave 2 (рекомендация):** tnt-customs (VERIFIED, B2B-чеки высокие), dentinn (VERIFIED, медтуризм), kiknadzedental-center (сырой шаблон-текст вместо кнопки записи), dental-stomus (рейтинг 4.8 при gmail), harley-street-clinic-dubai (год-в-имени ящика), route-hotel-tbilisi (нет движка), monteva-boutique-hotel (mail.ru брони), lincon (CN-маршрут без CN-версии), royal-core-aesthetic-clinic-llc («0 K+» на главной), solvex (два @ в email — письмо физически не дойдёт).

---

## Отчёт по статусам (обновлять после каждой сессии отправки)

| Статус | Кол-во |
|---|---|
| QUEUED | 41 + 25 − 1 (dolmama HOLD) = 65 |
| SENT | 0 |
| FU-DUE / FU-SENT | 0 |
| REPLIED (→ touch-log) | 0 |
| HOLD | 2 (dolmama, palm-tbilisi-boutique-hotel) |
| LOST (ист.) | 4 (Wave 0) |
| SKIPPED | 2 (APaven, Sher — см. аудиты) |

**Ожидаемая конверсия (Principle XIII, проверять по цифрам, не по вере):** reply 2–5% на cold → 17–18% на trigger-based. 25 писем первой волны = 1–4 ответа при trigger-качестве адресатов. Kill-criteria: 0 ответов на 25 отправок за 10 раб. дней → пересмотр писем (не канала).

**Связанные:** [touch-log.md](./touch-log.md) · [outreach-message-pack.md](../../../undreplans/docs/projects/underundre/content/2026-11-10-outreach-message-pack.md) · [discovery-call-kit.md](../../../undreplans/docs/projects/underundre/content/2026-11-10-discovery-call-kit.md) · мини-скрины: `<slug>/audit.md` в этой папке.
