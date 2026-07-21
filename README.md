# Aditya Gayal

**Software engineer building developer tools, backend systems and applied-AI products.**

Pune, India &middot; Third-year Computer Science

[LinkedIn](https://linkedin.com/in/aditya-gayal) &middot; [Email](mailto:gayaladitya9@gmail.com)

---

## What I Build

I design systems that produce measurable, inspectable evidence rather than opaque outputs.
My current focus is developer-tools infrastructure: how coding agents consume context, how candidates are ranked, and how civic data reaches citizens.
I value honest benchmarks, tests that fail when the code breaks, and documentation that matches the implementation.
Currently deepening: systems design, TypeScript monorepos, deterministic algorithm design, and open-source contribution practice.

---

## Flagship Work

### [Continuum](https://github.com/AntiDynamic/Continuum) &mdash; Coding-Agent Observability

> Vendor-neutral context observability and optimisation system for AI coding agents.

A TypeScript monorepo that sits *around* coding agents, capturing run telemetry without intercepting the model. Agents run normally; Continuum records what happened.

| Capability | Evidence |
|---|---|
| Run observation: git snapshots, test results, tool calls, file changes | `packages/agent-core/` |
| SQLite persistence with 9 versioned migrations and FTS5/BM25 search | `packages/database/src/migrations.ts` |
| MCP stdio server for AI-client context retrieval | `packages/mcp-server/` |
| Regex-based output redaction before storage | `packages/shared/src/redaction.ts` |
| Cross-platform CI matrix: Ubuntu + Windows, Node 22 + 24 | `.github/workflows/ci.yml` |
| 54 test files across 10 packages | `**/*.test.ts` across monorepo |
| Deterministic 24-case retrieval benchmark | `docs/retrieval-benchmark.md` |
| Codex App Server shadow observation (experimental) | `packages/codex-app-server/` |

**Evidence model:** Continuum measures only externally observable behaviour. It does not observe which files the model attended to or report provider billing.

---

### [Redrob Ranker](https://github.com/AntiDynamic/redrob-ranker) &mdash; Deterministic Candidate Ranking

> CPU-only deterministic ranker for the Redrob Intelligent Candidate Discovery challenge.

| Capability | Evidence |
|---|---|
| JSONL/GZIP streaming ingestion, CSV output | `src/redrob_ranker/io.py` |
| Career-history, skills, logistics, risk feature extraction | `src/redrob_ranker/features.py` |
| Weighted deterministic score, tie-broken ranking | `src/redrob_ranker/scoring.py` |
| Grounded per-candidate reasoning column | `src/redrob_ranker/reasoning.py` |
| 23 passing tests | `tests/`, `pytest -q` |
| No-network: standard library only, no hosted LLMs | `rank.py` |

**Development benchmark:** 100,000-candidate run completed in **111.27 seconds** on CPU (Windows x64, development machine).

---

### [ElectoGuide AI](https://github.com/AntiDynamic/electoguide-ai) &mdash; Civic Education Platform

> Nonpartisan election-education assistant: Gemini, Cloud NL, Firestore, Cloud Translation.

| Capability | Evidence |
|---|---|
| FastAPI async backend with Gemini streaming | `services/gemini_service.py` |
| Cloud Firestore session persistence | `services/firestore_service.py` |
| Cloud Translation (12 languages) | `services/translate_service.py` |
| Pydantic validation and slowapi rate limiting | `routes/chat.py` |
| Multi-stage Docker, non-root user | `Dockerfile` |
| 41 passing tests with mocked GCP services | `tests/` |
| Deployed on Cloud Run | [Live demo](https://electoguide-ai-991060611253.us-central1.run.app) |

---

## Selected Engineering Evidence

- **Cross-platform CI** &mdash; Ubuntu + Windows, Node 22 + 24 matrix
- **SQLite migrations** &mdash; 9 versioned schema migrations with FTS5 capability probing
- **MCP integration** &mdash; stdio server compatible with Claude Code and Gemini CLI
- **Deterministic ranking** &mdash; identical input produces identical ranked output
- **Regex redaction** &mdash; API keys and tokens stripped before database storage
- **Controlled benchmark** &mdash; 24 labelled retrieval cases, labels fixed before execution
- **Mocked external services** &mdash; all GCP APIs mocked in ElectoGuide tests
- **No-network guarantee** &mdash; Redrob Ranker runs on Python standard library only

---

## Current Focus

- Hardening Continuum context compiler: TypeScript AST extraction, SQL parsing, coverage-aware retrieval
- DSA and interview-level problem-solving practice
- Systems design through implementation
- Open-source contribution in developer-tools and backend spaces

---

## Contact

**Email:** gayaladitya9@gmail.com &middot; **GitHub:** [AntiDynamic](https://github.com/AntiDynamic) &middot; **LinkedIn:** [linkedin.com/in/aditya-gayal](https://linkedin.com/in/aditya-gayal)

> *All claims in this profile are backed by source code, tests, or CI workflows in the linked repositories.*