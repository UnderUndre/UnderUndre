# Forensic Workaround & Margin Leak Audit (Pre-Interview Discovery Memo)

**Client:** Botan Investments / MLVentures (Myna Labs, Inc. / ChaChat Ecosystem)  
**Delivery Model:** underundre.com (Solo Productized Engineering Bureau)  
**Date:** 2026-11-09  
**Mode:** B2B Services Delivery Economics / Consumer Mobile AI Infrastructure  
**Status:** PRE-INTERVIEW HYPOTHESIS REGISTER (CALIBRATED / OUTSIDE-IN)  
**Primary Suspected Constraint:** EXPERIMENTATION_THROUGHPUT_VS_ANALYTIC_CAPACITY (UNVERIFIED)

---

## 0. Executive Narrative (§0)

### Why You Received This Audit

I am conducting an independent, preliminary forensic audit of processes and data architecture based on the public job posting by Botan Investments / MLVentures for a Product Analyst position in their consumer AI division (ChaChat). My objective as an external systems auditor is to map out critical architectural and process crossroads prior to discussing operational tasks.

### What Caught My Attention

1. A stated requirement to support **500+ A/B tests annually** across mobile and web stacks with a single incoming analyst.
2. An explicit mandate for an autonomous **AI-powered analytics harness** (agentic workflows designed to take questions to insights within hours).
3. A broad scope of responsibility spanning end-to-end data pipelines (ClickHouse, Airflow) to monetization experiments (Adapty, RevenueCat).

### Most Plausible Explanation

*Preliminary hypothesis based on open data:* The rapid velocity of product hypothesis generation (1.4 tests/day) may be outpacing the capacity for rigorous statistical validation. The team is seeking to scale analytical throughput without proportionally inflating headcount by delegating initial triage to the specialist's personal agentic AI stack.

### Alternative Explanations

- **Alt 0 (Organic Growth / Mature Experimentation Platform):** The company already runs a mature platform with automated power calculations, sequential testing, and SRM safeguards; 500+ tests represents standard parallel traffic allocation across a multi-million user base.
- **Alt 5 (H₀ — Null Hypothesis):** Data pipelines are stable, tracking is friction-free, and hiring simply accommodates planned expansion into new locales and web surfaces.

### What to Verify in 5 Days

Request an anonymized register of the last 20 concluded A/B experiments documenting three parameters: multiple comparison correction methods (Bonferroni / FDR / CUPED), Sample Ratio Mismatch (SRM) status, and actual exposure duration.

### If You Only Have 60 Seconds (BLUF)

- **Primary Risk:** Risk of making product decisions based on statistically fragile signals under dense parallel test cadences without a centralized validation gateway.
- **Confidence:** Direction: `MODERATE`, Magnitude: `LOW` (strict ban on pseudo-precise percentages without L1 telemetry).
- **Data Required:** Proportion of experiments with logged SRM checks and the architecture of ClickHouse/Airflow pipelines.
- **First Step:** Calibrate the experimentation protocol and review statistical power calculation methodologies.
- **Probability That New Software Is Needed:** LOW (a Level 1 standard operating procedure and methodology alignment are sufficient).

---

## 1. Epistemic Horizon & Stakeholder Alignment

- **Beneficial Owner (Legal / Equity):** Victor Shaburov (historical beneficiary of Botan Investments; confirmed Looksery and AI Factory exits to Snap) / Paul (Peter) Shaburov (Managing Director of MLVentures, co-founder of Myna Labs, Inc.). Status: `VERIFIED (L1/L4)`.
- **Budget Authority ($5k+ Signing Authority):** Paul Shaburov / Alla Tabeleva (COO, MLVentures). Status: `UNVERIFIED` (hiring authority delegated; direct discretionary P&L access unconfirmed).
- **Process Sponsor:** Product Lead / Head of Growth, ChaChat.
- **JTBD Trigger Catalyst (90-Day Push):** Scaling ChaChat's multilingual user base, ramping paid performance marketing, and continuously optimizing paywall conversions for subscriptions (PRO) and microtransactions (Gems).
- **Master System of Record:** AppsFlyer, Adapty / RevenueCat (attribution and receipts), ClickHouse + Superset (custom analytics storage).
- **Economic Scale Status:** `UNKNOWN` (exact revenue for Myna Labs is undisclosed; millions in reach and 9,000+ App Store reviews publicly confirmed).
- **Telemetry Quality Triage (Principle XVI):** `YELLOW` (public job postings, storefront metrics; no direct access to raw database logs or ETL traces).
- **Observability Status:** `INDICATIVE_FRICTION_RANGE` (dollar leakage calculations strictly forbidden pending primary L1 receipts).
- **Discovery Failure Mode:** `NONE` (standard outside-in diagnostic mode).
- **Commercial Route Permitted:** `PRODUCT_1_GOVERNANCE` (Level 3 Custom Build locked).
- **Change Capacity Score (1–5):** `4 (Managed Adoption)` — the engineering culture is historically rooted in competitive programming (ACM ICPC), indicating high adaptability to complex algorithmic toolsets.
- **Primary Business Bottleneck (Goldratt TOC):** `CONVERSION_PLUMBING` (throughput of the hypothesis validation pipeline at the user onboarding, retention, and monetization stage).

---

## 2. Evidence Confidence Register & Hypothesis Tree

### Vacancy Synchrony Analysis

- **Observed Hiring Pattern:** Synchronous hiring of a Product Analyst (SQL/Python/ClickHouse/Airflow), a Customer Support Specialist (handling Stripe billing disputes and chargebacks), and a Head of Performance Marketing.
- **Engineering / Operational Interpretation:** The organization is scaling user acquisition while reinforcing customer support and transaction dispute operations. Hiring an analyst is synchronized with the objective of monetizing incoming paid traffic through paywall iteration.

### Cross-Validation Note (Mandatory Tone & Claim Retraction Protocol)
>
> *Second-pass validation: removing ungrounded assertiveness and separating verified artifacts from hypotheses.*
>
> 1. **Claim "500 tests per year is mathematically impossible / analytics is broken" — RETRACTED.** Booking, Meta, and mature mobile app teams run thousands of simultaneous tests on segmented audiences using sequential testing and CUPED. At scale, this is feasible. Downgraded to a risk hypothesis: *"Risk of accumulating Type I errors in the absence of centralized multiple-comparison safeguards."*
> 2. **Claim "The company actively practices p-hacking" — RETRACTED.** No direct evidence exists (e.g., p-value distributions, premature stopping logs, post-hoc metric swaps). Downgraded to a verifiable risk: *"Potential risk of false-positive wins during manual review cadences."*
> 3. **Claim "ChaChat is purely an NSFW cash-grab factory" — RETRACTED.** The application is legitimately distributed on the App Store (Lifestyle category, 4.37 rating across 9,300+ reviews) and Google Play. It operates as a full-featured consumer AI product featuring persistent personas, contextual memory, and voice/image generation.
> 4. **Claim "Compensation is drastically below market relative to developed economies" — RETRACTED.** Directly comparing a local Tbilisi package ($3,000 gross) against San Francisco aggregate salaries ignores regional tax frameworks (1% Small Business status in Georgia), remote flexibility, and local market baselines.

| Observed Factor / Signal | Direction (Existence) | Magnitude | Evidence Level (L1–L5) | Epistemic Blindspot (Required L1 Telemetry) |
| :--- | :---: | :---: | :--- | :--- |
| **High experimentation frequency (500+ tests)** | `CONFIRMED` | `[UNKNOWN]` | L4: Job posting | Internal A/B testing platform run logs |
| **Subscription-driven unit economics** | `CONFIRMED` | `[UNKNOWN]` | L1: App Store IAP tiers + L4: Vacancy | Cohort retention curves and LTV/CAC exports |
| **Use of agentic AI workflows in analytics** | `CONFIRMED` | `[UNKNOWN]` | L4: Vacancy specification | Internal repositories / automation scripts |
| **ClickHouse/Airflow data infrastructure** | `CONFIRMED` | `[UNKNOWN]` | L4: Tech stack specification | Data warehouse architectural diagrams |

### Working Competing Hypotheses

1. **Alt 0 (Healthy Growth / Mature Product Engine) — [Confidence Class: PLAUSIBLE]:** Scaling a proven consumer AI business model; traffic volume is sufficient to hit statistical power quickly, and hiring addresses planned operational expansion.
2. **Alt 1 (Leading Constraint Hypothesis: Experimentation Overload) — [Confidence Class: ACTIVE]:** The rate of product hypothesis generation is outpacing the validation capacity of the data team. Merging three roles (Data Engineering, BI, Product Analytics) into a single hire risks shallow evaluations.
3. **Alt 5 (Null Hypothesis — H₀) — [Confidence Class: UNCALIBRATED]:** Infrastructure is balanced, tracking operates without critical friction, and testing cadences are within normal industry tolerances for high-velocity consumer apps.

### Popperian Falsification Criteria
>
> *My leading hypothesis (Alt 1) will be formally FALSIFIED if:*  
> **Internal experimentation documentation demonstrates automated Minimum Detectable Effect (MDE) calculations, pre-experiment sample sizing, verified absence of SRM, and algorithmic multiple-comparison corrections across active experiments.**

---

## 3. Stress-Test Hypothesis Register (Outside-In Mode)

> ⚠️ **FALSE PRECISION REGULATION:** In Outside-In mode, lacking verified bank statements and primary transaction logs, exact dollar-loss estimations are strictly forbidden. Metrics are classified via qualitative risk bands.

| Friction / Leverage Point | Assessment / Range | Status | Confidence Class | Required Unlocking L1 Telemetry |
| :--- | :--- | :--- | :--- | :--- |
| **Type I Error Exposure (False Positives)** | Elevated risk of phantom wins under parallel testing without adjustments | `ACTIVE` | `MODERATE` | Experimentation platform specification |
| **Revenue Mix (Subscriptions vs. Gems)** | Predominance of recurring renewals over one-off microtransactions | `PLAUSIBLE` | `MODERATE` (L1 App Store) | RevenueCat / Adapty / Stripe transaction exports |
| **Role Functional Distribution** | Split focus across pipeline maintenance, BI reporting, and test design | `ACTIVE` | `HIGH` (L4 Job Spec) | Jira sprint logs / time tracking |
| **Long-Term Retention Stability** | Typical companion-app decay curve beyond D30–D60 | `PLAUSIBLE` | `UNCALIBRATED` | Amplitude / Mixpanel cohort curves |

---

## 4. Domain Asset Engine Block (The Client's Real Moat)

- **Mobile Distribution and ML Engineering Expertise:** Historical track record of the founders (Looksery, AI Factory) in scaling media-rich, high-throughput consumer applications across global app stores.
- **The Data Flywheel (Behavioral Interaction Dataset):** The continuous ingestion of proprietary user telemetry: conversational branching, context prompts, emotional retention triggers, voice sessions, and engagement-to-unlock patterns. If aggregated systematically to fine-tune character weights and predictive retention loops, this proprietary behavioral data—rather than commoditized foundational LLMs—constitutes the business's core defensible moat.
- **Product Iteration Velocity:** Capability to test and deploy UI/UX permutations across text, voice, and image modalities faster than traditional, slower-moving consumer apps.
- **Moat Vulnerabilities:** Platform dependency on App Store / Google Play developer guidelines regarding AI companions and mature content (18+), coupled with customer acquisition cost (CAC) volatility across Meta and TikTok ad auctions.

---

## 5. Pre-Mortem & Constraint Relocation Analysis

### 5.1. The Klein Pre-Mortem (Failure Scenarios at 6–12 Months)

1. **Vector 1 (Drift Toward Unplanned Data Engineering):** The analyst ends up spending significant working hours manually maintaining Airflow DAGs and reconciling ClickHouse schemas, resulting in ad-hoc, under-designed A/B test setups.
2. **Vector 2 (Statistical Signal Erosion):** Pushing to hit 500+ tests using uncalibrated AI scripts increases the risk of adopting product decisions on noisy, under-powered data, gradually degrading underlying unit economics.
3. **Vector 3 (Platform Policy Adjustments):** Stricter app store regulations on generative personas or subscription billing mechanics dampen baseline conversion rates, rendering micro-optimizations from UI tests negligible.

### 5.2. Constraint Relocation Forecast (Goldratt Step 5)

- **Primary Relieved Constraint:** Turnaround time on analytical data modeling and experimentation design.
- **Immediate Downstream Bottleneck:** Mobile development throughput (iOS/Web engineers), who will become the physical gating factor for implementing validated test winners.
- **Preventative Safeguard:** Upfront backlog filtering: greenlighting only those changes where projected effect sizes exceed measurement noise by a significant margin.

---

## 6. The Hierarchy of Interventions & Productization

- **Reversibility Rating:** `HIGH (Two-Way Door)` (analytical frameworks and experimentation SOPs are easily adjustable).
- **Implementation Blindfold Check:**  
  *Query:* Would I recommend this intervention if legally barred from selling implementation software?  
  *Result:* `PASS` (recommendations focus entirely on governance, operational playbooks, and methodology).

### Recommended Levels

- **Level 0: Do Nothing (Status Quo):** `REJECTED` (scaling experiment volume without structured statistical gates invites decision degradation).
- **Level 1: Process / SOP Change ($0 CAPEX):** `RECOMMENDED`.
  1. *Experimentation SOP:* Enforce a standardized Experiment Design Doc requiring pre-launch MDE, sample-size targets, and defined evaluation windows.
  2. *Data Hygiene Protocol:* Mandate automated Sample Ratio Mismatch (SRM) checks prior to reading out test results.
  3. *Scope Demarcation:* Formally separate analytical engineering (ETL/DWH) from core product hypothesis design.
- **Level 2: Buy COTS SaaS:** `HOLD` (existing stack covers functional requirements; supplementary tooling will not solve foundational process discipline).
- **Level 3: Deploy Sovereign Bypass / Custom Build:** `HARD LOCKED` (no custom software justified; unverified primary L1 telemetry).

### 6.1. Productization Opportunities (Product Discovery Lens)

- **Standardizable Assets:**
  - *Experimentation Governance Framework:* Pre-flight validation checklist (SRM checks, MDE verification, multiple-testing correction templates).
  - *AI Analytics Harness Review:* Operating standard for validating AI-generated analytical outputs against hallucination and skewed aggregations.
- **Replicable Artifact:** Modular experimentation governance playbook tailored for high-velocity consumer AI applications.

---

## 7. 🛑 AUTOMATION PROHIBITED LIST (VIA NEGATIVA)

- **Automated Rollouts via LLM Decisioning:** Strictly prohibit rolling out variants to 100% production purely based on AI-agent conclusions without engineer sign-off on confidence intervals and group balance.
- **Short-Window Subscription Optimization:** Forbid evaluating subscription price elasticity solely on Day 1 conversion rates, which ignores downstream cancellation curves and refund/chargeback patterns over a full billing cycle.

---

## 8. Final Diagnostic Verdict

```yaml
verdict: LEVEL_1_PROCESS_SOP
primary_defect: UNVERIFIED
suspected_primary_constraint: "EXPERIMENTATION_THROUGHPUT_VS_ANALYTIC_CAPACITY"
beneficial_owner_verified: true
budget_authority_verified: false
telemetry_quality: YELLOW
data_mode: OUTSIDE-IN
discovery_failure_mode: NONE
commercial_route: PRODUCT_1_GOVERNANCE
null_hypothesis_active: true
growth_hypothesis_active: true
change_capacity_score: 4
economic_buyer_aligned: false
blindfold_check: PASS
evidence_class:
  - L1_REGISTRY_TELEMETRY: false
  - L2_OBSERVED: false
  - L3_HEURISTIC: false
  - L4_OSINT: true
  - L5_MARKETING: true
reversibility: HIGH
confidence:
  direction: MODERATE
  magnitude: LOW
epistemic_confidence_class: PLAUSIBLE
likely_next_constraint: "ENGINEERING_IMPLEMENTATION_BANDWIDTH"
falsification_criteria: "Provision of internal experimentation documentation demonstrating systemic controls for MDE, SRM, peeking, and multiple-comparison adjustments."
pre_mortem_top_risk: "The analytics function becomes encumbered by data pipeline maintenance and rapid ad-hoc reporting, increasing the risk of decisions being made on statistically fragile signals."
recommended_immediate_action: "Conduct a 5-day experimentation audit: evaluate p-value distributions and check for multiple-testing corrections across the last 20 concluded tests."
```
