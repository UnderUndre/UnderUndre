# Forensic Workaround & Margin Leak Audit (Pre-Interview Discovery Memo)

**Client:** Cal.com, Inc. (Delaware C-Corp, File #5792440; formerly Calendso, Inc.)  
**Delivery Model:** Solo Productized Engineering Bureau (UnderUndre)  
**Date:** 2026-11-04  
**Mode:** B2B Services & SaaS Delivery Economics  
**Status:** PRE-INTERVIEW HYPOTHESIS REGISTER  
**Primary Suspected Constraint:** `COST_ATTRIBUTION_DEBT_CAUSED_BY_UNVERIFIED_OPEN_CORE_ECONOMICS` (UNVERIFIED)

---

## 0. Why you received this audit

I am Andrei, founder of underundre.com — a one-person productized engineering bureau focused on quantifying operational friction. I prepared this pre-interview discovery memo for Cal.com from public data — no vendors, no pitch deck, just a falsifiable read of your open-core economics.

### What caught my attention

1. April 15, 2026 bifurcation: production moved to a private repository; `calcom/cal.diy` released as a stripped MIT fork.
2. A verified license-validation bug affecting self-hosted paid flows (Issue #26610, fixed in `deployments.service.ts`).
3. Hiring concentrated on Enterprise productization (Senior Product Designer, Enterprise Fullstack Engineers).
4. ~50k stars / 16k forks / 1.2k open issues — with no public cohort data linking `cal.diy` users to closed Enterprise contracts.

Usually such a set means the company cannot yet tell whether its open-source tail is a customer acquisition engine or an operational leak.

### Most likely explanation

Cost attribution debt: engineering hours consumed by non-revenue community issues, with no end-to-end attribution from fork to closed-won Enterprise contracts. This is a preliminary, open-data hypothesis; competing explanations and falsification criteria are inside the audit.

### Alternative explanations

- Healthy growth: the split was clean IP isolation; friction is normal Series A scaling.
- The fork is an efficient CAC engine — gating the tracker would then be a revenue hazard.
- Null hypothesis: open-source overhead is absorbed within tolerance; no intervention required.

### What to check in 5 days

Retrospective source attribution on the last 20 closed Enterprise Organizations deals: how many originated from self-hosted `cal.diy` setups?

### If you only have 60 seconds

- **Preliminary conclusion:** the open-core economics are unattributed, not broken.
- **Confidence:** low (direction capped at 60%; magnitude unproven).
- **Data needed:** Linear issue-to-customer-tier export; core SWE time on non-contract issues; deal origination.
- **Suggested first step:** the 20-deal attribution retrospective above.
- **Probability that new software is needed:** low (recommended actions are $0 SOPs, strictly conditional).

---

## 1. Epistemic Horizon & Stakeholder Alignment

- **Economic Buyer (P&L Owner):** Peer Richelsen & Bailey Pumfleet (Co-founders & Co-CEOs). *Signing Authority Status (Gate 1):* `(b) Partner consensus / Board approval required [AUTHORITY UNVERIFIED]`. Discretionary authorization limit (≥ \5,000$) is governed by Delaware C-Corp bylaws and not publicly disclosed. Level 3 (Build) is locked pending in-person verification.
- **Process Sponsor:** Keith Williams (Head of Engineering). Direct accountability for core throughput, CI/CD health, and release stability of the private enterprise monorepo.
- **JTBD Trigger Catalyst (90-Day Push / Gate 9):** Institutional codebase bifurcation on April 15, 2026 — migration of production code to a private repository and release of the stripped-down `calcom/cal.diy` (MIT) with Enterprise modules excised (Teams, Orgs, SAML/SSO, Workflows). This induced operational turbulence in the tracker and made the core unit economics question urgent: does the public fork justify its maintenance overhead?
- **Observed Vector of Investment (OSINT Evidence, L4):**; Public hiring of Senior Product Designer (100k–150k USD) and Enterprise Fullstack Engineers confirms revealed resource allocation: capital is concentrated on commercial productization of complex B2B features (Organizations, Routing Forms, SSO). The `cal.com/open` portal confirms macro-observability (salary bands, headcount ~40–44 FTE, commit velocity).
- **Master System of Record (Gate 4):** GitHub Enterprise + Linear + Stripe Billing + PostgreSQL.
- **Economic Scale Status (Gate 8):** `Band (d): $5M+/yr (ARR ~$5.1M, OpEx >$250k/mo)`. Baseline loaded rate for Senior SWE: **75–110 USD/hr**.
- **Observability Status:** `MACRO_OBSERVABLE / TIER_ATTRIBUTION_UNVERIFIED`. Macro metrics are transparent, but granular telemetry is absent: the company lacks time-tracking telemetry linking senior engineering hours to client tiers.
- **Change Capacity Score (1–5 / Gate 3):** `NOT_VERIFIED [ESTIMATED_RANGE: 2–4, HYPOTHESIS]`. Deployment velocity is high (thousands of commits, rapid architectural pivot to closed-source core). However, team behavioral adherence to strict ticket-filtering SOPs requires interview calibration.
- **Political Sabotage & Friction Vectors:**; *Who loses leverage if the tracker is gated?* DevRel and community managers whose KPIs tie to GitHub stars and vanity open-source metrics; founders whose personal brand relies on a 100% "Open Startup" ethos.
- **Primary Business Bottleneck (Goldratt TOC / Gate 2):** `HYPOTHESIS: CONVERSION_PLUMBING & FULFILLMENT OVERFLOW (IN_SCOPE)`. Requires ruling out a commercial top-of-funnel collapse (Demand Generation Collapse).

---

### ⚠️ Board-Level Strategic Dilemma

```text
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                              BOARD-LEVEL STRATEGIC DILEMMA                             │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ Question:      Does the public Cal.diy fork generate measurable revenue attribution    │
│                in the Enterprise Organizations tier?                                   │
│ Evidence:      [IDENTIFIER NOT FOUND]                                                  │
│ Impact:        FOUNDATIONAL (Dictates the viability of the entire business model).     │
│ Conclusion:    Without this metric, it is impossible to prove whether community effort │
│                is an efficient Customer Acquisition Cost (CAC) or operational waste    │
│                and engineering margin leak.                                            │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Evidence Confidence Register & Hypothesis Tree

### Leading Hypothesis Tree

- **Core Hypothesis:** `Cost Attribution Debt in Open-Core Architecture`; *Sub-Hypothesis A (Support Spillover):* Core engineers unintentionally spend high-loaded hours ($90/hr) triaging and debugging non-revenue `cal.diy` community bugs. *Sub-Hypothesis B (Conversion Blindspot):* The company lacks end-to-end attribution linking a `cal.diy` fork user to a closed-won Enterprise Organizations contract ($28/user/mo).

| Friction Point / Observation | Direction Conf. (Existence) | Magnitude Conf. (Scale) | Primary Evidence (Level L1–L5) | Epistemic Blindspot (Required Telemetry) |
| :--- | :---: | :---: | :--- | :--- |
| **Open-Core Community Drag** | **60%** (Capped) | **15%** | L4 (OSINT: ~50k stars, 16k forks, 1.2k issues) + L5 (Code bifurcation announcement) | Linear/GitHub export: `User -> Issue ID -> Customer Tier (Free vs Paid)`. |
| **Context-Switching Tax (K ≥ 2)** | **50%** | **10%** | L4 (Dual-repo architecture: private core vs `cal.diy` fork) | Anonymized time-tracking CSV or git activity logs with commit time deltas `[ID NOT FOUND]`. |
| **Open-Core Conversion Visibility Gap** | **60%** (Capped) | **0%** | L4 (Absence of public cohort conversion funnels on `cal.com/open`) | End-to-end pipeline: `Telemetry ID / Domain Hash -> Closed Won Enterprise Deals`. |
| **License & Encryption Key Debugging** (Issue #26610) | **95%** | **40%** | L1 (Fix commit in `deployments.service.ts`) + L1 (Issue #26610) | Support ticket logs showing HTTP 401 errors from paid enterprise accounts. |

*(Note: Confidence for OSINT-derived findings is strictly capped at 60% Direction and 20% Magnitude until L1/L2 telemetry is verified).*

### Working Competing Hypotheses

1. **Alt 0 (Healthy Growth Hypothesis — Null Growth Hypothesis):** Observed repository friction and designer/engineer hiring are normal symptoms of healthy Series A scaling outgrowing early-stage ad-hoc operations. The April 15, 2026 split was a deliberate, clean IP isolation from community forks without creating internal organizational drag.
2. **Alt 1 (Operational Drain):** The unpaid `cal.diy` tail leeches core engineering capacity, cannibalizing focus on enterprise roadmap delivery.
3. **Alt 2 (Licensing & Architecture Clashes):** Divergence between the private monorepo and public code causes persistent sync failures and license validation bugs.
4. **Alt 3 (Integration Delivery Friction):** The primary constraint is not community noise, but asynchronous external calendar race conditions (Google/Microsoft Graph APIs) in `EventManager.ts` (Issue #28705).
5. **Alt 4 (Scope / Support Spillover):** Enterprise accounts demand custom integration changes disguised as standard warranty support.
6. **Alt 5 (Null Hypothesis — H₀):** Operational pipelines and issue triage operate within acceptable industrial margins; open-source overhead is minimal, absorbed asynchronously, and does not degrade margins; no intervention required.

### Required Disconfirming Evidence Search
>
> *Active search to disprove the leading hypothesis (Cost Attribution Debt):*  
> The auditor must inspect the origination source of the last 20 closed Enterprise deals. If ≥ 50% originated directly from self-hosted `cal.diy` setups, and Linear logs show core SWEs spend <5% of sprint capacity on the public repository, the leading hypothesis is **falsified**. In that scenario, open-source support is an ultra-efficient acquisition engine (CAC), not an operational leak.

### Popperian Falsification Criteria
>
> *The leading hypothesis will be formally FALSIFIED if:*  
> **Anonymized Linear exports over the last 90 days demonstrate that total Core SWE time spent on non-contract/community issues averages less than 3 hours per week per engineer.**

---

## 3. Cost of Workaround & Friction Ledger (Calibration Model)

> ⚠️ **EPISTEMIC DISCLAIMER:** This ledger is a **calibrated heuristic stress-test** based on verified organizational scale (Gate 8: Band d, loaded rate 75–90 USD/hr) and observed signals. Without direct database extracts, these figures DO NOT constitute audited financial data.

**CoW(Lite) = C(FTE) + C(SaaS) + C(Scrap)**
**where C(FTE) = Σ (Reported Hours × W(evidence) × Loaded Rate × 52)**

| Friction Point / Observed Cost Signal | Reported Volume | Evidence Level | Weight ($W$) | Loaded Rate | Stress-Test CoW | Epistemic Class |
| :--- | :--- | :--- | :---: | :--- | :--- | :--- |
| **Self-Hosted License Validation Failures** (Issue #26610) | 10 hrs/wk (Model) | Level 1 (Issues/PR) | **1.0** | $75 / hr | `[UNVERIFIED]` | `[MODEL_PENDING_TELEMETRY]` |
| **Redundant Tool Sprawl (C_{SaaS)** (Linear + Intercom + Zendesk) | Duplicate seats | Level 1 (Invoices) | **1.0** | Flat Fee | `[UNVERIFIED]` | `[PENDING_INVOICE_AUDIT]` |
| **Support Escalation Spillover** (Core SWEs in public tracker) | Unverified | Level 4 (OSINT/Issues) | **0.3** | $90 / hr | `[UNVERIFIED]` | `[HEURISTIC_OSINT]` |
| **Context Switching Tax (K ≥ 2)** | 20–40% focus penalty | Level 4 (Model) | **0.3** | $90 / hr | `[UNVERIFIED]` | `[HEURISTIC: WEINBERG_MODEL]` |
| **TOTAL CONFIRMED FLOOR (HARD FLOOR):** | — | — | — | — | **IDENTIFIER_NOT_FOUND** | `[NO_SYNTHETIC_PRECISION]` |

*Auditor Ruling on Financials:* Publishing synthetic dollar totals prior to accessing primary telemetry is strictly prohibited. Observed operational cost signals are `PRESENT`, but the exact financial damage remains legally and mathematically unproven.

---

## 4. Pre-Mortem & Constraint Relocation Analysis

### 4.1. The Klein Pre-Mortem (Failure Vector Analysis at Month 6)

*Assume the triage gating intervention was implemented, but the project failed completely by Month 6. The top 3 fatal failure vectors are:*

1. **Vector 1 (Political / Brand Backlash):** Mandatory license verification for issue creation sparked a developer outrage on Hacker News ("Cal.com abandons Open Source"), throttling organic virality and damaging top-of-funnel enterprise lead flow.
2. **Vector 2 (Operational / False Positives):** Enterprise buyers piloting `cal.diy` locally before purchasing hit a closed door in the issue tracker, assumed the project was unmaintained, and migrated to Calendly/SavvyCal.
3. **Vector 3 (Executive Sabotage):** Founders and core engineers bypassed the gate by answering bug reports directly in Discord and X (Twitter), collapsing process discipline.

### 4.2. Constraint Relocation Forecast (Goldratt Step 5)

- **Current Suspected Constraint:** Unattributed engineering hours consumed by public repository maintenance.
- **Immediate Downstream Constraint Migration:** Once core engineers are shielded from community noise, the bottleneck will immediately relocate to **Enterprise Delivery & Onboarding**. The new constraint will be custom integration velocity (configuring SSO/SCIM across disparate IdPs and integrating with on-premise Microsoft Exchange servers).
- **Mitigation Directive:** Standardize the Enterprise Onboarding SOP and build a pre-flight verification checklist before gating the public issue tracker.

---

## 5. The Hierarchy of Interventions (Traversal Gate)

- **Reversibility Rating (Bezos Type 1 vs Type 2):** `HIGH (Two-Way Door)`. Adjusting or reverting issue-gating policies on GitHub takes under 15 minutes in repository settings. High reversibility permits action at ≥ 60% confidence.
- **Implementation Blindfold Check:**; *Query:* Would the bureau recommend this audit and these protocols if legally barred from selling implementation services?; *Result:* **`PASS (Unbiased)`**. The bureau offers no custom development here; the core deliverable is an analytical stress-test for $490 and $0 CAPEX operational SOPs.

### Level 0: Do Nothing (Status Quo)

- **Verdict:** `UNDER_EVALUATION`.
- **Economic Rationale:** Contingent on validating Alt 0 (Healthy Growth) and Alt 5 (Null Hypothesis). If the community proves net-positive as an organic acquisition engine, maintaining the status quo is optimal.

### Level 1: Process / SOP Change ($0 CAPEX)

- **Verdict:** `CANDIDATE_INTERVENTION (Conditional on Conversion Telemetry)`.
- **Candidate Implementation:**
  1. *Candidate SOP-01:* Channel segregation: move `cal.diy` issues to `Discussions-only`; require a corporate license token (`License SHA-256`) for bug reports in the private monorepo.
  2. *Candidate SOP-02:* Rotating sprint on-call: assign 1 engineer per sprint to triage external PRs, fully isolating the remaining core team.
- **Unlock Condition:** Enforced strictly if cohort analysis reveals near-zero conversion from `cal.diy` to paid contracts. If conversion is positive, gating creates an immediate revenue hazard.

### Level 2: Buy COTS SaaS

- **Verdict:** `DEFERRED_PENDING_TELEMETRY`.
- **Economic Rationale:** Evaluating AI-triage or enterprise support add-ons is deferred until actual volume is verified. If developer drain is confirmed, COTS tooling may be cheaper than internal management overhead.

### Level 3: Deploy Sovereign Bypass (Custom Build)

- **Verdict:** `DEFERRED_PENDING_ATTRIBUTION_ANALYSIS`.
- **Economic Rationale:** Custom software development cannot be justified at the discovery phase (`NOT_EVALUABLE_AT_DISCOVERY_STAGE`). Custom tooling requires proven SaaS exhaustion and Change Capacity ≥ 4.

---

### 5.1. Productization Opportunities (Product Discovery Lens)

- **Standardized Nodes:**
  1. *Enterprise License Verification Gate:* Reusable GitHub Action / Webhook validating client license hashes before allowing bug ticket creation.
  2. *Self-Hosted Diagnostic CLI:* Automated environment pre-flight utility (checking OAuth configurations, `CALENDSO_ENCRYPTION_KEY` consistency, DB connectivity) prior to submitting tickets.
- **Reusable Artifact:** Open-source pre-flight triage utility for commercial open-core repositories (FOSS Utility).
- **Product Scalability:** High. Isolating free community noise from commercial SLAs is an industry-wide challenge across all COSS vendors pivoting from AGPL to commercial dual-licensing (e.g., PostHog, Supabase, Gitlab).

---

## 6. 🛑 AUTOMATION PROHIBITED LIST (VIA NEGATIVA)

- **AI Auto-Responders on Public GitHub Issues:** Prohibited during discovery. Hallucinates, extends issue threads, and forces senior developers to spend time debunking bot responses.
- **Granular Engineer Time-Tracking (Jira Tempo):** Prohibited. In Cal.com's open engineering culture, this triggers Goodhart's Law and leads to metrics corruption.
- **Custom-Built Licensing Connectors:** Prohibited. The `data.status` bug in `deployments.service.ts` is resolved with an in-place patch in 15 minutes, not by engineering a new microservice.

---

## 7. Investor-Grade Stress Test

```text
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                               INVESTOR-GRADE STRESS TEST                               │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ Test Question: If Cal.diy completely disappeared tomorrow:                            │
│                would Enterprise ARR decrease, remain unchanged, or increase?           │
│ Evidence:      [IDENTIFIER NOT FOUND]                                                  │
│                                                                                        │
│ Three Valid Outcomes:                                                                  │
│ 1. ARR DOWN:   Cal.diy is an efficient CAC engine and essential marketing asset.       │
│                Gating or restricting the tracker is contraindicated.                   │
│ 2. ARR FLAT:   Cal.diy is operational waste and pure support drag.                     │
│                Proceed immediately with Level 1 SOP issue gating.                      │
│ 3. ARR UP:     Cal.diy is cannibalizing commercial software sales.                     │
│                Recommended: Board-level strategic review of licensing terms,          │
│                functional boundaries, and commercial upgrade paths.                   │
│                Immediate action: [IDENTIFIER NOT FOUND / PENDING REVIEW].              │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 8. Final Diagnostic Verdict

```yaml
verdict: LEVEL_0_DO_NOTHING
primary_defect: UNVERIFIED
suspected_primary_constraint: COST_ATTRIBUTION_DEBT_CAUSED_BY_UNVERIFIED_OPEN_CORE_ECONOMICS
null_hypothesis_active: true
growth_hypothesis_active: true
change_capacity_score: NOT_VERIFIED_RANGE_2_TO_4
economic_buyer_aligned: probable_unverified
blindfold_check: PASS
evidence_class:
  - L1_TELEMETRY: true (Specific commits & Issue #26610)
  - L2_OBSERVED: false
  - L3_HEURISTIC: true
  - L4_OSINT: true (GitHub metrics, cal.com/open, job postings)
  - L5_MARKETING: true (Code bifurcation announcement)
reversibility: HIGH
direction_confidence: 60% (Capped: relies on L4 OSINT signals)
magnitude_confidence: 15% (Capped: zero raw time telemetry)
intervention_confidence: 50%
likely_next_constraint: "Enterprise Onboarding & Complex IdP/Exchange Integration Capacity"
falsification_criteria: "Linear time exports showing <3 hrs/wk per Core SWE spent on non-contract issues, combined with >50% of closed Enterprise deals originating from cal.diy self-hosted instances."
pre_mortem_top_risk: "Public backlash against perceived abandonment of open-source ethos damaging top-of-funnel inbound pipeline."
recommended_immediate_action: "Days 1-5 (Stage 0): Conduct retrospective source attribution on the last 20 closed Enterprise Organizations deals to evaluate Alt 0 (Healthy Growth) and answer the Investor-Grade Stress Test prior to introducing operational friction."
```

---
