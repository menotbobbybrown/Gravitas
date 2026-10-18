# Gravitas Next-Generation Research Notes

Status: working notes. arXiv entries below are **candidate reading** taken from
the mission brief — **not yet verified** (no network fetch performed this
session). Do not cite them as supporting evidence until version, date, authors,
and results are confirmed. Verified items are marked **[verified local]**.

## 1. Verified local findings (code + tests, HEAD `9fe0839`)

| # | Mechanism | What we confirmed | Gap it closes |
|---|-----------|-------------------|---------------|
| 1 | Schema-gated `cmd_report` **[verified local]** | `validate_episodes` without schema returned `[]` errors; crafted contradiction aggregated. Fixed + tested this session | Honesty gate (issue #27) |
| 2 | OpenCode read ledger **[verified local]** | Guard passed `reads=set()`; every existing-file edit denied. Shim now records reads per-session; guard enforces | Host parity F1 |
| 3 | Aggregate-skip in compare/metrics **[verified local]** | Raw glob + `KeyError` on stored aggregates. Fixed + tested | Bench robustness |
| 4 | Empty-report guard **[verified local]** | Empty input exited 0 with empty table. Now exit 1 | Anti-gaming |

## 2. Candidate external reading (UNVERIFIED — fetch before using)

Harness engineering: Meta-Harness, Agentic Harness Engineering, Adaptive
Auto-Harness, Harness Engineering source-code study, Scaffold Effect in Coding
Agents. Evaluation: Harness-Bench, Harness-IF, SWE-bench (+ known limitations).
Interfaces/search/verification: SWE-agent, Agentless, scaling agentic verifiers,
tool-augmented reasoning, search-based repair, test-time compute allocation,
differential/metamorphic testing, hierarchical retrieval, memory compression,
planning under uncertainty, model-router economics, prompt injection vs agents,
multi-agent vs single-agent empirical work.

Rule: for each paper record research question, setup, finding, limitations,
candidate Gravitas mechanism, existing equivalent, cost, falsifiable experiment,
and build/drop verdict. No paper counts until its experiment section is read.

## 3. Competitor implementation study (NOT STARTED — diffable surface planned)

Targets: SWE-agent, Agentless, gemini-cli, opencode, codex, OpenHands, aider
(execution loop, context construction, file tools, search, policy, memory,
retry, planning, tracing, patch/test selection, failure recovery). Pin commits
before comparing. Never claim a public repo exposes a proprietary model's
internal reasoning.

## 4. Developer-report corpus (NOT STARTED)

Collect Gemini/Claude-Code/weak-model failure reports (lost context, repeated
broken fix, wrong-file edits, dropped requirements, tool loops, quota burn,
parallel conflicts, compaction loss, green tests with broken behavior, false
"done", silent hooks, overaggressive policy). Label each anecdotal / reproduced
/ corroborated. Social-media consensus is not evidence.

## 5. What NOT to build (standing)

- Vector-DB / embedding retrieval as a default dependency (privacy, cost).
- Agent swarms without measured benefit per task family.
- Mandatory planning ceremony for trivial tasks.
- Self-modifying harness without human promotion gate.
- New overlapping frameworks where a scoped fix to an existing module suffices.
