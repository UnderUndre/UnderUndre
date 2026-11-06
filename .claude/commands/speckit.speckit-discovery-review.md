---
description: Independent external adversarial forensic review of the two-layer SpecKit Discovery memo (clients/*/workaround-audit.md): Layer 1 — Trigger Memo §0 (≤250 words, «Почему вы получили этот аудит» + 60-second BLUF) and Layer 2 — Full Forensic Body. Enforces zero-trust on TDABC math (time haircuts), Principle XVI Telemetry Quality (GREEN/YELLOW/RED, Lens Q), Owner ≠ Authority separation (Lens R), Probability Calibration (Lens S), False Precision (Lens T), OSINT confidence ceilings (60/20), Alt 0 + Null hypotheses, Budget Reality Check (Principle XIV), Productization (§5.1), Narrative red-team vectors, and render hygiene.
handoffs:
  - label: Forensic Web Research
    agent: internet-research
    prompt: Run forensic OSINT web research to verify local regulatory fines, salary benchmarks, and COTS SaaS pricing
  - label: Rebuild Narrative
    agent: speckit.narrative
    prompt: Rewrite the Trigger Memo §0 according to the review findings and re-run the chain
  - label: Red-Team Narrative
    agent: speckit.red-team-narrative
    prompt: Adversarially verify the rebuilt Trigger Memo against the 9 narrative attack vectors
---

## User Input

```text
$ARGUMENTS
```

Optional: `--path <path/to/audit.md>`, `--provider <claude|codex|antigravity|gemini|copilot>`, `--layer <1|2|both>` (default: both).

ultrathink
> "Ревьюер обязан защищать аудит от профессиональной деформации инженера. Если автор насчитал экономию со слов испуганной секретарши без дисконта 50%, если нарисовал '$9,522' из воздуха вместо диапазона, если спутал учредителя из выписки с тем, кто реально подписывает чеки, если полез считать ROI по чатам в Telegram при полном блэкауте телеметрии или выдал клиенту §0 с сырым TeX'ом вместо текста — такое заключение отправляется в шредер. Двухслойный меморандум проверяется как ЕДИНОЕ целое: Layer 1 без Layer 2 — голословие, Layer 2 без Layer 1 — непрочитанный гений." — Valera

## Goal

Run a ground-truthed adversarial review of a **two-layer SpecKit Discovery memo** before presentation to the economic buyer ($350–$490 Product 0 Tripwire).

The memo MUST contain both layers (Principle XV, Constitution):

1. **Layer 1 — Trigger Memo (§0, ≤250 prose words):** «Почему вы получили этот аудит» → «Что привлекло внимание» → «Наиболее вероятное объяснение» (preliminary) → «Альтернативные объяснения» (вкл. Null/Healthy) → «Что проверить за 5 дней» → «Если у вас есть только 60 секунд» (BLUF: риск / уверенность / данные / первый шаг / вероятность нового софта).
2. **Layer 2 — Full Forensic Body:** TDABC Lite v2 with haircuts, hypothesis tree with ceilings, falsification criteria, Pre-Mortem, Hierarchy of Interventions (4-Level Gate & Product 0→1→2 Route), Productization (§5.1), Via Negativa list, verdict YAML.

The memo must be free from:

1. **Authority Conflation (Owner ≠ Authority Blindness):** conflating legal/equity registry ownership with personal discretionary P&L signing authority ≥ $5,000, or pitching solutions to operational managers who cannot authorize funds.
2. **Telemetry Contamination & ROI Hallucination:** calculating dollar ROI or CoW on RED telemetry (chats, unestimated tickets, bulk Friday timesheets) under `OBSERVABILITY_BLACKOUT` (Principle XVI).
3. **Pseudo-Precision & Uncalibrated Probabilities:** writing accountant-precise numbers like `$9,522` without primary receipts, or guessing arbitrary probabilities like `47%` or `Alt 0 = 50%` without an empirical Bayesian model.
4. **TDAGU (Time-Driven Approximate Guessing):** inflated savings from unverified verbal claims without the mandatory 50% haircut.
5. **Operational Imperialism:** forcing software onto a business whose real constraint is marketing, lead flow, or cash insolvency.
6. **Staffing Theater:** presenting UnderUndre as an enterprise multi-head consultancy instead of a transparent solo engineering bureau.
7. **GO-Bias / Audit Overkill:** recommending the paid audit where the Budget Reality Check fails (audit cost ≥ pain cost) — a NO-GO verdict documented with full rigor is a WIN, not a failure (Principle XIV).
8. **Narrative Bullshit:** asserted diagnoses, hallucinated ROI, hidden Null hypothesis, or internal jargon leaking into the client-facing §0.

---

## Audit Dimensions (Lenses A–T)

### Layer 2 — Forensic Body (Lenses A–J)

| ID | Lens | Forensic Stress Probes & Mandatory Checks |
| :--- | :--- | :--- |
| **A** | **Economic Buyer Alignment** | Did the audit verify and separate Beneficial Owner vs. Budget Authority (`budget_authority_verified`)? If the sponsor is an operational manager, is the owner's buy-in documented? (See also Lens R). |
| **B** | **TOC & Out-of-Scope Probe** | Is the primary constraint genuinely operational? If the company suffers from top-of-funnel starvation (no leads), did the audit issue an **`OUT_OF_SCOPE`** verdict? |
| **C** | **Anti-TDAGU Time Haircut** | Were verbal employee time estimates subjected to the mandatory **50% haircut**? If raw reported hours were used at face value, flag as HIGH defect. |
| **D** | **Change Capacity Realism** | Was the client's past implementation track record probed? If Change Capacity ≤ 2/5, is custom software (Level 3) strictly rejected? |
| **E** | **Hierarchy of Interventions (4-Level Gate & Product Route)** | Did the audit honestly test Level 0 (Do Nothing) and Level 1 (Process SOP) before Level 2/3? Was a $0 delegation matrix evaluated? Does Level 3 name the **Default Implementation Route** (undreseller template / Sprint A) and respect the Product 0→1→2 commercial gating? |
| **F** | **Variance & Pain Pattern** | Were episodic regulatory risks (e.g. AML / Trakheesi fines) separated from continuous daily labor drag? |
| **G** | **Solo Bureau Authenticity** | Does the audit avoid corporate staffing fluff ("our consulting team") and accurately state solo productized execution? |
| **H** | **COTS SaaS Ground Truth** | Did the author investigate existing off-the-shelf tools with current pricing before rejecting Level 2? |
| **I** | **Via Negativa Authenticity** | Is the Automation Prohibited List populated with a real, high-friction process that is banned from code? |
| **J** | **Epistemic Class Tagging** | Are all numbers, rates, and payback metrics tagged with `[VERIFIED]`, `[HEURISTIC]`, or `[HYPOTHESIS]`? Are OSINT-derived findings capped at 60% Direction / 20% Magnitude? |

### Productization & Reality (Lenses K–L)

| ID | Lens | Forensic Stress Probes & Mandatory Checks |
| :--- | :--- | :--- |
| **K** | **Productization (§5.1, Product Discovery Lead)** | Is the Productization Opportunities section filled with a standardized pattern and a named тиражируемый артефакт (undreseller module / SOP pack / COTS config)? Is the "local pain vs market-wide pain" question answered? |
| **L** | **Budget Reality Check (Principle XIV, NO-GO Honesty)** | Does the audit compare the audit fee ($350–490) against the annual cost of the suspected pain / hired role? If audit cost ≥ pain cost (e.g. a $500/mo role), the verdict MUST be **`NO_GO_PRODUCT_0`** documented with the same rigor as a GO — finding, budget arithmetic, content-case angle, re-verification triggers. A GO verdict against failing budget arithmetic = CRITICAL GO-bias defect. |

### Layer 1 — Narrative (Lenses M–P)

| ID | Lens | Forensic Stress Probes & Mandatory Checks |
| :--- | :--- | :--- |
| **M** | **Trigger Memo Structure** | ≤250 prose words; 6 blocks in canon order; BLUF block answers all 5 points (риск / уверенность / данные / первый шаг / вероятность нового софта). Block NOT titled "Executive Summary" (it gets skipped) — canon: «Почему вы получили этот аудит». |
| **N** | **Signal ≠ Diagnosis** | Client layer speaks in signal form («я заметил сигнал X. Обычно он связан с A/B/C. Для проверки нужны данные D») — never «у вас проблема X». No magnitude numbers without L1/L2 evidence (OSINT ceiling: ≤60% Direction, ≤20% Magnitude). Null/Healthy alternative present if live in the audit. |
| **O** | **Voice & Jargon Canon** | First person singular = **Андрей (Andrei), founder** — never «мы» (except quoted market voice), never Валера (internal AI persona). No internal jargon in client layer: TOC, Goldratt, TDABC, Bayes, Pre-Mortem, Level 0–3, Change Capacity, W-weights. Language matches the market (RU/EN). |
| **P** | **Render Hygiene** | The memo MUST survive common markdown viewers: zero `$$`-LaTeX and raw TeX (`\text{`, `\times`, `\le`) — Unicode instead (× ≤ ≥ ↔ → H₀); zero paired-money math (`$X–$Y` → `X–Y USD`); zero 2-space nested lists (flatten into parent with «;»); angle-bracket risk (`<50M` → «до 50M»); no `![][imageN]` broken refs in client artifacts. A client opening the memo in Google Docs / hh mail / ZCode viewer must see clean text. |

### Telemetry Quality, Authority & Calibration (Lenses Q–T)

| ID | Lens | Forensic Stress Probes & Mandatory Checks |
| :--- | :--- | :--- |
| **Q** | **Telemetry Quality Gate (Principle XVI / Zero-GIGO)** | Was Three-Color Telemetry Triage (GREEN / YELLOW / RED) executed? If telemetry is RED (chats, unestimated backlog tickets, bulk Friday timesheets), is `OBSERVABILITY_BLACKOUT` declared? Are RED data used for dollar leakage / CoW / ROI estimation? (**CRITICAL defect** if true — Principle XVI strictly forbids dollar math on RED telemetry). Is Product 2 (Build) locked until GREEN telemetry proves an active operational bottleneck with projected ROI ≥ 5×? Is Product 1 capped at YELLOW? Is the commercial route (`Product 0 → 1 → 2`) aligned with telemetry quality? |
| **R** | **Authority Separation (Owner ≠ Authority)** | Are `beneficial_owner_verified` and `budget_authority_verified` explicitly bifurcated? Did the author conflate legal/equity ownership in a public registry with discretionary personal P&L signing authority ≥ $5,000? If the interviewee is an operational manager or delegate with unverified/zero signing power, is Product 2 (Build / Level 3) strictly **HARD LOCKED**? If the Economic Buyer refused access, is `DISCOVERY_FAILURE_MODE: NO_AUTHORITY` recorded? |
| **S** | **Probability Calibration (Anti-Pseudo-Precision in Hypotheses)** | Are hypothesis probabilities stated as arbitrary point numbers from the head (e.g. `P = 47%`, `P = 63%`, or unsubstantiated `Alt 0 = 50%`) without an empirical Bayesian model or reference class? Are qualitative epistemic confidence classes enforced instead: `ACTIVE`, `PLAUSIBLE`, `LIKELY`, `UNCALIBRATED` (or strictly bounded binary 50/50 priors)? Any pseudo-precise probability percentage without an explicit calculation model must be flagged as a defect. |
| **T** | **False Precision (Anti-Heuristic Bookkeeping)** | Does the audit report exact cents or pseudo-exact dollar amounts (e.g. `$9,522/yr`, `$14,318`) on heuristic, interview-derived, or OSINT data? If L1/L2 primary receipts are missing, did the author enforce **calibrated ranges** (e.g. `5k–10k USD range` or `~9k–10k USD`) instead of pseudo-accounting? Any exact dollar figure on L3/L4/L5 without an explicit range or rounding must be flagged as a defect (heuristic presented as accounting fact). |

---

## Severity Rules & Verdict Gate

- **CRITICAL**: Dealbreaker.
  - Treats top-of-funnel sales crisis as an operational software problem (missed Out-of-Scope);
  - Raw verbal time claims used without haircut to engineer fake ROI;
  - **Using RED telemetry (chats, unestimated tickets, bulk timesheets) for dollar leakage / ROI calculation (Principle XVI breach — Lens Q)**;
  - Recommends custom build (Product 2 / Level 3) despite Change Capacity ≤ 2, missing budget authority (`budget_authority_verified: false/unverified` — Lens R), or without GREEN telemetry (Lens Q);
  - Omits Via Negativa list;
  - **GO verdict where Budget Reality Check fails (audit fee ≥ pain cost)**;
  - §0 asserts a diagnosis or hallucinated ROI.
- **HIGH**:
  - Unverified or conflated Economic Buyer / Budget Authority (Owner ≠ Authority conflation — Lens R);
  - Missing Telemetry Quality Triage (GREEN/YELLOW/RED missing — Lens Q);
  - Pseudo-precise dollar amounts on heuristic data without ranges (Lens T false precision);
  - Arbitrary point probabilities in hypotheses without an empirical model (Lens S uncalibrated probability);
  - Missing Vacancy Synchrony Analysis when hiring signals are present;
  - Missing variance profiling; corporate staffing theater;
  - **Missing or broken Layer 1 (no §0 / >250 words / missing BLUF / "Executive Summary" naming)**;
  - **Render breakage in client layer (raw TeX, paired $, 2-space nested lists)**;
  - Internal jargon leaked into §0.
- **MEDIUM**:
  - Minor hourly rate calculation discrepancies (<20%);
  - Incomplete COTS SaaS feature matrix;
  - §0 word count 250–290 (soft breach);
  - Minor tone drift.
- **LOW**: Minor formatting or typographical imperfections.

| Verdict | Condition | Action |
| :--- | :--- | :--- |
| **PASS** | 0 CRITICAL, 0 HIGH | Ready to deliver to client / economic buyer. |
| **REWORK** | 0 CRITICAL, 1–2 HIGH | Apply haircuts, verify buyer, rebuild §0 via `speckit.narrative` + `speckit.red-team-narrative`, fix render, and re-run. |
| **REJECT** | ≥ 1 CRITICAL or >2 HIGH | **DO NOT DELIVER**. Total rewrite required: audit suffers from vendor bias. |

**Layer coupling rule:** Layer 2 defects never PASS because Layer 1 is beautiful, and vice versa. Both layers must independently reach PASS.

---

## Output Format

```yaml
discovery_review_verdict: PASS | REWORK | REJECT
provider: <claude|codex|antigravity|gemini|copilot>
findings:
  - lens: A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T
    severity: CRITICAL | HIGH | MEDIUM | LOW
    quote: "[exact quote from the memo]"
    problem: "[what fails the lens]"
    fix: "[concrete replacement, not 'rephrase']"
layer1_narrative:
  present: true | false
  word_count: NN (prose, excl. headings/IDs)
  blocks_order_ok: true | false
  bluf_complete: true | false
  naming_canon_ok: true | false
layer2_forensic:
  tdabc_haircuts_ok: true | false
  ceilings_ok: true | false
  falsification_present: true | false
  via_negativa_present: true | false
  productization_present: true | false
telemetry_quality_gate:
  triage: GREEN | YELLOW | RED
  observability_blackout_respected: true | false
  red_telemetry_in_roi: true | false
  commercial_route_aligned: true | false
authority_separation:
  owner_verified: true | false
  authority_verified: true | false
  owner_equals_authority_conflated: true | false
  build_locked_if_no_authority: true | false
calibration_and_precision:
  probability_classes_used: true | false
  false_precision_free: true | false
  vacancy_synchrony_analyzed: true | false | N/A
budget_reality_check:
  audit_fee: "$350-490"
  annual_pain_cost: "KNOWN | UNKNOWN (fine — that is what the audit measures) | BELOW_AUDIT"
  no_go_honesty_ok: true | false
render_hygiene:
  latex_free: true | false
  paired_dollar_free: true | false
  nested_lists_flat: true | false
  image_refs_clean: true | false
```

---

## Review Flow (chain of custody)

```
speckit.speckit-discovery (двухслойный драфт)
  → speckit.narrative (§0 Trigger Memo)
  → speckit.red-team-narrative (9 векторов атаки на §0)
  → speckit.speckit-discovery-review (ЭТОТ файл: A–T по обоим слоям)
  → PASS → Final Memo → отправка → строка в outreach-touch-log
```

**Rule:** this review does NOT replace `speckit.red-team-narrative` — the narrative gets its own adversarial pass. This review verifies the memo as a whole deliverable: math, gates, narrative, render, and the honesty of the verdict itself (GO, HOLD, and NO-GO must all be equally rigorous — a documented NO-GO with budget arithmetic is a first-class outcome of this pipeline).
