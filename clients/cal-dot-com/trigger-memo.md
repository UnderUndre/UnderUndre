# Trigger Memo — Cal.com (Executive Narrative, ≤250 words)

**Source audit:** [`workaround-audit.md`](./workaround-audit.md) | **Narrative Type:** Null Hypothesis Narrative (+ Support Leak) | **Date:** 2026-11-05
**Chain of custody:** `speckit.narrative` draft → `speckit.red-team-narrative` REVISE (1 finding, fix applied) → **PASS**

---

## Why you received this audit

I am Andrei, founder of UnderUndre — a one-person productized engineering bureau focused on quantifying operational friction. I prepared this pre-interview discovery memo for Cal.com from public data — no vendors, no pitch deck, just a falsifiable read of your open-core economics.

## What caught my attention

1. April 15, 2026 bifurcation: production moved to a private repository; `calcom/cal.diy` released as a stripped MIT fork.
2. A verified license-validation bug affecting self-hosted paid flows (Issue #26610, fixed in `deployments.service.ts`).
3. Hiring concentrated on Enterprise productization (Senior Product Designer, Enterprise Fullstack Engineers).
4. ~50k stars / 16k forks / 1.2k open issues — with no public cohort data linking `cal.diy` users to closed Enterprise contracts.

Usually such a set means the company cannot yet tell whether its open-source tail is a customer acquisition engine or an operational leak.

## Most likely explanation

Cost attribution debt: engineering hours consumed by non-revenue community issues, with no end-to-end attribution from fork to closed-won Enterprise contracts. This is a preliminary, open-data hypothesis; competing explanations and falsification criteria are inside the audit.

## Alternative explanations

- Healthy growth: the split was clean IP isolation; friction is normal Series A scaling.
- The fork is an efficient CAC engine — gating the tracker would then be a revenue hazard.
- Null hypothesis: open-source overhead is absorbed within tolerance; no intervention required.

## What to check in 5 days

Retrospective source attribution on the last 20 closed Enterprise Organizations deals: how many originated from self-hosted `cal.diy` setups?

## If you only have 60 seconds

- **Preliminary conclusion:** the open-core economics are unattributed, not broken.
- **Confidence:** low (direction capped at 60%; magnitude unproven).
- **Data needed:** Linear issue-to-customer-tier export; core SWE time on non-contract issues; deal origination.
- **Suggested first step:** the 20-deal attribution retrospective above.
- **Probability that new software is needed:** low (recommended actions are $0 SOPs, strictly conditional).

---

## Red Team Narrative — Verdict

```yaml
narrative_redteam_verdict: PASS
findings:
  - vector: solution_bias
    quote: "gating the public issue tracker would be contraindicated (draft v1)"
    problem: "Narrative hinted at a specific intervention (tracker gating) before attribution analysis; audit verdict is LEVEL_0_DO_NOTHING with conditional SOPs"
    fix: "Interventions removed from client layer; replaced with the neutral 20-deal attribution retrospective; '$0 SOPs, strictly conditional' in BLUF"
  - vector: hidden_assumptions
    quote: "(draft v1 omitted Alt 0)"
    problem: "Healthy-growth alternative (clean IP isolation, normal Series A scaling) was missing from the front layer"
    fix: "Added to Alternative explanations; Null hypothesis kept explicit"
traceability_check: "every claim traces to audit (bifurcation date, Issue #26610 L1, hiring signals, falsification criteria, verdict yaml)"
uncertainty_preserved: true
word_count: 243 (prose tokens; headings, markup & identifier tokens excluded)
```
