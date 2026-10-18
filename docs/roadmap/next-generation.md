# Next-Generation Roadmap

Parent epic: this file. Child issues are created on GitHub (links below) and
deduplicated against issue #27. Priority: P0 correctness/security/bench
blockers, P1 high-impact, P2 experimental, plus research/host/integration.

## P0 — Correctness / security / benchmark blockers
- [ ] #27 Bench report pipeline never validates episodes — fixed on
  `ascension/phase-b-foundation` (schema-gated `cmd_report` + empty/aggregate
  guards + regression tests); merge vs contributor PR #56, then close.
- [ ] #68 Ledger rewrite without anchor passes verification (evidence forgery).
- [ ] #70 Lifecycle fixture corpus + stale-shim detection (malformed payloads,
  renames, concurrency, timeouts, uninitialized sessions).

## P1 — High-impact engineering
- [x] OpenCode read-before-write parity (shim ledger + session-scoped guard) —
  implemented + tested this session.
- [ ] #57 Recovery doc contradiction (`recovery.md` no-re-read vs enforced
  read-before-write) — doc fix + re-read-after-resume rule.
- [ ] #58 Reproducer identity binding (argv-to-contract like validators).
- [ ] #59 Shell-write freshness invalidation beyond enumerable redirects.

## P2 — Experimental (feature-flagged)
- [ ] #60 Task-conditioned context scout (deterministic retrieval, token budgets).
- [ ] #61 Failure-guided debugging protocol (repro → hypotheses → discriminating
  experiments → minimal fix).
- [ ] #62 Adversarial verifier (boundary/property/differential checks in sandbox).
- [ ] #67 Bounded patch tournament for hard bugs (2–3 candidates, isolated worktrees).
- [ ] #63 Trace linter (repeat-action, thrash, stale-evidence detectors).
- [ ] #69 Offline harness optimizer (falsifiable contracts + human gate) — do not
  start before #63 lands.
- [ ] #71 Canonicalize paths at record time (`good first issue`).

## Research / replication tasks
- [ ] #64 Harness-engineering literature verification pass.
- [ ] Competitor teardown with pinned commits (SWE-agent, Agentless, aider,
  gemini-cli, opencode, codex, OpenHands) — not yet filed; file after #64.
- [ ] Developer-report corpus with anecdotal/reproduced/corroborated labels —
  fold into competitor teardown issue.

## Host integration
- [ ] #65 OpenCode `tool.execute.after` payload audit across versions.
- [ ] #70 Antigravity/OpenCode lifecycle fixture corpus + stale-shim detection.

## Beginner-friendly
- [ ] #66 Seeded reproducible benchmark task (licensed repo + hidden validator).
- [ ] #71 Canonicalize paths at record time (replaces the cross-platform matrix item).
