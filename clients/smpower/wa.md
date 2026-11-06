# ФОРЕНЗИК-ДИАГНОСТИКА: SPECKIT DISCOVERY DOSSIER

## §0. ПОЧЕМУ ВЫ ПОЛУЧИЛИ ЭТОТ АУДИТ

*(Executive Narrative Front Layer — 185 слов, строго $\le 250$, zero-jargon)*

**Почему вы получили этот аудит**  
Я — Андрей Матуляк, независимый системный инженер. Пишу по поводу активного расширения команды Smart IT Power LLC в ереванском офисе на ул. Дереника Демирчяна, 2/3.

**Что привлекло внимание**  
Синхронный поиск трех специалистов в офис: разработчик .NET/C# (hh.ru `139062931`), технический писатель (hh.ru `138935605`) и специалист ручного тестирования мобильных и веб-приложений (hh.ru `138430147`).

**Наиболее вероятное объяснение**  
Предварительно по открытым данным: усиление контура клиентских приложений. Подобный набор сигналов часто возникает, когда команды сталкиваются с ростом нагрузки на документирование, согласование контрактов интерфейсов и ручную приемку релизов.

**Альтернативные объяснения**  
Плановое здоровое расширение: запуск новой продуктовой вертикали, где параллельный наем разработки, фиксации документации и контроля качества — естественный шаг сборки конвейера.

**Что проверить за 5 дней**  
Длительность цикла регрессионного тестирования мобильных сборок и процент возврата задач на доработку между тестированием и разработкой.

**Если у вас есть только 60 секунд (BLUF)**  

- **Главный риск:** Задержка релизов на этапе ручной проверки при росте затрат на разработку.
- **Уверенность:** Предварительная, по открытым источникам (до знакомства с внутренними данными).
- **Что нужно:** Анонимизированная выгрузка закрытых задач за 60 дней.
- **Первый шаг:** Согласование схем API до начала кодинга без закупки нового софта.
- **Нужен ли новый софт:** Маловероятно. По открытым данным очевидного дефицита базовых инструментов не обнаружено.

---

## §1. ЭПИСТЕМИЧЕСКИЙ ГОРИЗОНТ И СТЕЙКХОЛДЕРЫ

- **Economic Buyer (L1 Реестр РА):** Andrei Harhun (Андрей Гаргун, 100% доли ООО «Smart IT Power LLC»).
- **Operational P&L Authority ($5k+):** `[HYPOTHESIS / UNVERIFIED]` — подлежит валидации на Stage 0 Gate 1 (распоряжается ли Гаргун бюджетом лично или делегировал право подписи операционному директору).
- **Инвентарь инструментов (COTS Inventory):**
  - Задачи: Jira / YouTrack `[VERIFIED IN STACK]`
  - Документация: Confluence `[VERIFIED IN STACK]`
  - API: Swagger / REST `[VERIFIED IN STACK]`
  - Логи: Elasticsearch `[VERIFIED IN STACK]`
  - Вердикт по закупке нового SaaS: `STRICTLY REJECTED` (инструментов достаточно, проблема в протоколах передачи).
- **Change Capacity Score (1–5):** `3 [HEURISTIC]` (Офисный онсайт позволяет внедрять регламенты административно).

---

## §2. ГИПОТЕЗЫ И АНАЛИТИЧЕСКИЕ ЛИНЗЫ

### Баланс гипотез (50 / 50)

1. **Alt 0 (Healthy Growth / Maturation, P = 50%):** Компания открывает новое клиентское направление (iOS/Android). Триада «Разработчик + Писатель + Тестировщик» — естественный минимальный жизнеспособный конвейер.
2. **Ведущая гипотеза трения (Triad Decoupling, P = 50%):** Рассинхрон между бэкендом и фронтендом. Из-за отсутствия жестких контрактов бэкендеры пишут API «по месту», техпис пытается задокументировать это задним числом, а ручной тестировщик вручную ловит регрессы перед выкаткой сборок.

---

## §3. КАЛИБРОВАННАЯ TDABC LITE V2 МОДЕЛЬ ТРЕНИЯ

> ⚠️ **EPISTEMIC DISCLAIMER:** Эвристическая модель с обязательным дисконтом: `Reported` $\to$ `-50% Haircut` $\to$ `W_OSINT (0.3)` $\to$ `Accepted Drag`.

$$\text{Modeled Hours} = \text{Reported Drag} \times 0.5 \times 0.3$$
$$\text{Expected Annual Drag} = P(\text{Constraint} = 0.5) \times \sum (\text{Modeled Hours} \times \text{Rate} \times 52)$$

| Источник трения в Триаде | Базовый эстимейт | Haircut (-50%) | Вес L4 (0.3) | Accepted Drag | Ставка в час | Годовой стресс-тест ($P=1.0$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Continuous: Ковыряние бэкендеров в логах ES** | 4.0 ч/нед | 2.0 ч/нед | 0.3 | 0.6 ч/нед (6 Devs) | $45/ч `[HEURISTIC]` | **$8,424 / год** |
| **Continuous: Задержка ручного регресса (QA)** | 8.0 ч/нед | 4.0 ч/нед | 0.3 | 1.2 ч/нед (2 QA) | $25/ч `[HEURISTIC]` | **$3,120 / год** |
| **Episodic: Скрап переделок из-за дрейфа ТЗ/Swagger** | — | — | — | Фиксированный скрап | — | **$7,500 / год** |
| **ИТОГО СТРЕСС-ТЕСТ ($P = 1.0$):** | — | — | — | — | — | **$19,044 / год** |
| **МАТЕМАТИЧЕСКОЕ ОЖИДАНИЕ ($P = 0.5$):** | — | — | — | — | — | **$9,522 / год** `[HEURISTIC]` |

*Вывод:* Потери порядка $9.5k/год полностью оправдывают покупку диагностического трипваера за $490 (ROI > 19x), но намертво блокируют продажу любой кастомной разработки ($5k+), пока цифры не подтверждены реальной базой данных.

---

## §4. DORA ACQUISITION & TELEMETRY TRIAGE (STAGE 0)

До передачи CSV-экспортов действует принцип XVI Конституции (Evidence Triage):

- **GREEN (Git / CI/CD):** Прямой расчет Lead Time for Changes и Change Failure Rate.
- **YELLOW (Jira/YouTrack):** Анализ с обязательным дисконтом 50% на списанные часы.
- **RED (Чаты / Отсутствие эстимейтов):** Вердикт `Observability Blackout` $\to$ запрет расчетов.

**Запрашиваемые метрики для проверки Alt 0 vs Clog:**

1. *Cycle Time:* Время жизни тикета от статуса «In Progress» у .NET Dev до «Passed QA» на мобильной сборке.
2. *Bug Bounce Rate:* Доля задач, возвращенных тестировщиком разработчику с формулировкой «работает не по логике / расхождение с документацией».
3. *Log Investigation Ratio:* Доля времени бэкендеров, уходящая на разбор инцидентов в Elasticsearch без предварительно воспроизведенного тест-кейса.

## §4.1. DISCOVERY FAILURE MODES & NO-GO TAXONOMY

Аудит за $490 считается на 100% успешно выполненным, если на этапе Stage 0 фиксируется любой из пяти исходов:

| Код исхода | Триггер / Условие в данных | Терминальное действие аудитора | Финансовый исход для клиента |
| :--- | :--- | :--- | :--- |
| **MODE_A: TELEMETRY_UNAVAILABLE** | Клиент отказывается предоставить CSV или расшарить экран с реальным процессом. | `ABORT_TRIGGER_2`. Немедленная остановка аудита. Возврат депозита при нулевом доступе. | Нулевые затраты на внедрение. Защита от слепой стройки. |
| **MODE_B: TELEMETRY_TOXIC** | Выгрузка трекера показывает «8 часов по пятницам», тикеты без эстимейтов, учет ведется в чатах. | Выдача вердикта `OBSERVABILITY_BLACKOUT`. Блокировка любых расчетов утечек. Назначение $0 SOP. | Запрет на покупку софта/спринтов до наведения порядка в учете. |
| **MODE_C: NO_AUTHORITY_ACCESS** | На интервью присутствует делегат без права распоряжения P&L $\ge \$5,000$ (нет доступа к Гаргуну/директору). | `ABORT_TRIGGER_1`. Отчет маркируется как `RECONNAISSANCE_ONLY`. Запрет коммерческих предложений. | Сохранение бюджета до подключения реального ЛПР. |
| **MODE_D: CONSTRAINT_DISPROVEN** | Данные Jira/Git показывают Bug Bounce Rate < 5%, регресс мобилки < 2 часов. Течь отсутствует. | Вердикт `LEVEL_0_DO_NOTHING`. Гипотеза проблем в триаде официально закрыта. | **Чистая экономия:** клиент НЕ сжигает $5k–$15k на ненужные реформы. |
| **MODE_E: HEALTHY_SCALING_CONFIRMED** | Выручка и транзакции растут быстрее, чем фонд оплаты труда. Найм триады — чистый рост (Alt 0). | Вердикт `ALT_0_VALIDATED`. Поздравление клиента, фиксация нормы конвейера, выход из сделки. | Подтверждение здоровья бизнеса внешним независимым аудитором. |

---

## §5. ИЕРАРХИЯ ВМЕШАТЕЛЬСТВ И ТИРАЖИРУЕМЫЙ АРТЕФАКТ

- **Reversibility Rating:** `HIGH (Two-Way Door)`
- **Implementation Blindfold Check:** `PASS` (Аудит не продает софт)

- **Level 0 (Do Nothing):** `HOLD` (Ждем проверки гипотезы Alt 0 через DORA-метрики).
- **Level 1 (Process / $0 SOP):** `RECOMMENDED`
  - Регламент **Contract-First**: бэкенд не приступает к кодингу контроллеров .NET, пока схема Swagger не утверждена техписателем (`138935605`) и QA (`138430147`).
  - Стандартизация логирования: добавление `CorrelationId / TraceId` в запросы клиентских приложений для мгновенной фильтрации в Elasticsearch без ручных раскопок.
- **Level 2 (COTS SaaS):** `REJECTED` (Инструменты уже есть).
- **Level 3 (Build Custom):** `STRICTLY LOCKED`.

### 5.1. Тиражируемый артефакт (Productization Lens)

- **Продукт:** `Triad Contract Governance Pack` (Product 1: $1,500–$2,500).
- **Input:** Спецификации OpenAPI/Swagger + чек-листы ручного тестирования.
- **Process:** Автоматизированный линтинг через Spectral CLI + генерация скелетов тестов Postman.
- **Output:** Готовый гейт для CI/CD, блокирующий мерж бэкенда при дрейфе схемы, плюс автосгенерированная документация для Confluence.

---

## §6. ФИНАЛЬНЫЙ СТАТУС ДИАГНОСТИКИ

```yaml
verdict: LEVEL_1_PROCESS_SOP
primary_defect: UNVERIFIED
suspected_primary_constraint: TRIAD_CONTRACT_DRIFT_AND_MANUAL_REGRESSION
alt_0_status: ACTIVE_CO_EQUAL
alt_0_confidence: UNCALIBRATED_PRIORS
change_capacity_score: 3 [HEURISTIC]
beneficial_owner_verified: true # Andrei Harhun (L1 TIN 02901535)
budget_authority_verified: false # Requires Stage 0 Gate 1
blindfold_check: PASS
active_vacancies_analyzed:
  - tech_writer: "138935605"
  - dotnet_dev: "139062931"
  - manual_qa: "138430147"
reversibility: HIGH
direction_confidence: 60% [L4 OSINT CEILING]
magnitude_confidence: 20% [L4 OSINT CEILING]
stress_test_friction_range: "$10,000 - $20,000 / yr" [HEURISTIC_RANGE]
expected_friction_midpoint: "$5,000 - $10,000 / yr" [UNCALIBRATED]
commercial_ladder_gates:
  product_0_discovery_tripwire_490: 
    status: GO
    asymmetry_ratio: ">10x against heuristic midpoint"
  product_1_governance_sop_pack:
    status: CONDITIONALLY_LOCKED
    unlock_condition: "telemetry_triage in [GREEN, YELLOW] AND budget_authority_verified == true"
  product_2_sovereign_build:
    status: STRICTLY_LOCKED
    unlock_condition: "telemetry_triage == GREEN AND roi >= 5x"
discovery_failure_mode_guards:
  - MODE_A_TELEMETRY_UNAVAILABLE: "ABORT_AND_REFUND"
  - MODE_B_TELEMETRY_TOXIC: "OBSERVABILITY_BLACKOUT_SOP_ONLY"
  - MODE_C_NO_AUTHORITY: "RECONNAISSANCE_MEMO_ONLY"
  - MODE_D_CONSTRAINT_DISPROVEN: "LEVEL_0_SAVINGS_CAPTURED"
  - MODE_E_HEALTHY_SCALING: "ALT_0_VALIDATED_CONGRATULATE_CLIENT"
recommended_immediate_action: "Execute 20-minute Stage 0 intake with Andrei Harhun or authorized P&L delegate; run Telemetry Triage on 60-day Jira/Git CSV extract"
```

---
