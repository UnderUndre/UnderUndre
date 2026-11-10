# Mini-Screen: Worldgran Logistics (Варшава) — Outside-In Hypothesis Register
**Client:** Worldgran Logistics (Варшава, Польша; Транспорт и экспедиция)
**Site:** https://worldgran.pl/ | **Контакт:** Email: worldgranlogistics@gmail.com; Тел.: +48 690 188 99373
**Date:** 2026-11-10 | **Mode:** OUTSIDE-IN (OSINT-only)
**Source:** реестр «B2B Funnel Audit Outside Russia» (Артефакт 2.4, строка 12) — данные внешнего ресерча, приняты через нуль-траст вход.
**Verdict:** GO-PRELIMINARY | **Верификация:** UNVERIFIED: LEVEL 3 (данные внешнего ресерча «B2B Funnel Audit Outside Russia», спот-чек не проводился)

## L2 Артефакты (из реестра ресерча)
- Дефект воронки: На домене worldgran.pl используется бесплатная почта worldgranlogistics@gmail.com, отсутствует англоязычная версия для международных перевозчиков (только польский интерфейс Uzyskaj wycenę swojego transportu)73.
- Живость бизнеса: Действующий логистический оператор (ul. Rudnickiego 8 lok 4, Warszawa)73

## Hypothesis Register
**H1 (UNVERIFIED):** расчёт ставки только вручную (нет калькулятора, глухая форма/WhatsApp) → сейлз-операционка съедает маржу. *проверка:* тестовый квоут, замер скорости и канала ответа.
**H2 (UNVERIFIED):** gmail/mail.ru в B2B-ВЭД теряет международных клиентов (Китай/ЕС). *проверка:* доля EN/CN-версии сайта и язык квоута.

## Персонализация
«Часто за этим стоит» — [заполнить при отправке из сегментного шаблона outreach-message-pack; соответствие сегменту: C4/C-логистика-ВЭД].

## Порядок в пайплайне
Внесён в `outreach-pipeline.md` (волна «Funnel Audit»), статус QUEUED. Перед отправкой: живость ссылки + WHOIS/email-домен.
