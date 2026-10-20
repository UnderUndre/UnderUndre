# 2026-10-07 — zcode — Verification of grok-4.7.md review (002-dogfood-portal)

## What was done
Independent verification of `repos/undreseller/specs/002-dogfood-portal/reviews/grok-4.7.md` against current `spec.md` / `plan.md` / `tasks.md` (read in full) plus older reviews (gemini-3.8-flash, keenetic-red-team-audit — skimmed verdicts).

## Key findings
- Grok 4.7 claims verified: RAM arithmetic 13.5 GB ✓ (recomputed); spec self-contradiction Cal.com vs Cal.diy (spec.md:6,14,58,64,113); `DIRECT_URL` misuse in plan.md:50 AND spec.md:64 (US2, contradicts FR-06 spec.md:111); NFR-04 "PITR" = actually RPO 6h dump (spec.md:120); Vercel serverless ↔ nftables-default-drop Postgres unreachable (plan.md:29,48-55 vs spec.md:118) — critical; shared_buffers 1.5GB in 2.0GB envelope (spec.md:28); shared Redis 0.5GB SPOF; PageSpeed gate absent from tasks.md; no Trailblazer URL; no VPS region.
- Additions Grok missed: (1) portal's own Next.js container absent from RAM budget — all three proposed hosting fixes put it on CPX42 (+0.5–1 GB unbudgeted); (2) `CalculatorLog` in FR-06 but missing from plan.md Phase 1 schema; (3) plan.md "Inngest Serverless SDK / BullMQ" either/or ambiguity — BullMQ would need a worker container, also unbudgeted.
- Downgraded: "company name in Telegram = PII" — residual risk, not critical.
- Verdict: agree with substance, disagree with label — not [NEEDS MINOR TWEAKS] but spec revision (self-contradicting contract). Constitution Principle VI: /speckit.implement remains blocked (no PASS from ≥2 external reviewers).

## Artifacts
- Verification report delivered in chat (no spec edits — user asked for review, not fixes).

## Follow-ups
- ~~Day-0 fix list~~ → **APPLIED** (user: «захуячь», same session).

## Applied fixes (Day-0 → spec.md / plan.md / tasks.md)
1. **Hosting topology**: Vercel/CF Pages excluded; whole Next.js App Router runs as `portal` container on CPX42 behind cloudflared (new clarification Session 2026-10-07; plan.md Summary §5, Technical Context, Target Platform). Postgres without `ports:` on host.
2. **RAM budget rebuilt**: portal 0.6 GB added; chatwoot 3.0→2.5 (Puma single + Sidekiq 5), outline 1.2→1.0 → sum 13.4 GB, host buffer 2.6 GB (cap ≤13.5, buffer ≥2.6 — NFR-03 updated).
3. **DSN discipline**: US2 Independent Test + plan submit route → `DATABASE_URL` (PgBouncer 6432); DIRECT_URL = migrate/DDL/pg_dump only.
4. **Memory**: shared_buffers 1.5GB→512MB (effective_cache_size to host page cache); redis `noeviction` + alert + second instance for queues on pressure; Cal.diy/portal builds banned on VPS → CI (GH Actions → GHCR).
5. **Backup honesty → true PITR**: pgBackRest/WAL-G base 6h + continuous WAL (archive_timeout 60s, RPO ≤ 5 min), two copies (Storage Box AND B2) object-lock ≥30d, missed-backup alert, T-027 restore-test gate before first production lead.
6. **Naming sweep**: US2/FR-08/routes/components → Cal.diy (`webhooks/caldiy`, `CalDiyEmbed.tsx`); header stripped of Plane/Supabase RLS/Trigger.dev; Inngest Cloud in-process chosen (BullMQ dropped → no worker container).
7. **Small stuff**: region `fsn1` fixed; `<TRAILBLAZER_URL>` placeholder contract in FR-02/T-007 (founder fills before publish); Arcade/Storylane click-to-play + RAM telemetry lazy (NFR-01); new T-028 Lighthouse CI gate (PS ≥95, FCP <0.8s, LCP <1.5s); `CalculatorLog` added to plan schema + T-002; admin SSH via Cloudflare Access (NFR-02).

## Verification
- grep sweep: zero leftovers of calcom/CalComEmbed/Inngest Serverless/BullMQ-as-runner/Vercel-as-platform; Vercel appears only in exclusion clauses; DIRECT_URL only in migrate contexts; sum recomputed 13.4.
- git diff --stat: 3 files, +55/−43.
- Legit remaining mentions: spec.md:42 (license Q&A history), spec.md:38/plan.md:24 (BullMQ in "without BullMQ"/eviction warning), spec.md:93 (Supabase DDL = Tripwire deliverable for client stacks, not our stack).

## Open items
- `<TRAILBLAZER_URL>` — founder must fill before publish.
- Next: re-review (grok-4.8 / next external pass) to unlock Constitution Principle VI gate for /speckit.implement.
