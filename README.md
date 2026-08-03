<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=6E56CF&height=150&section=header" alt="" width="100%" />
</p>

# Karthick — Senior Technical Architect & AI Infrastructure Engineer 👋

Senior engineer focused on building production-grade systems that are robust, observable, and cost-effective. I design and ship test-first backends, large‑scale LLM/agent tooling, resilient RAG pipelines, and accessible TypeScript frontends — all backed by reproducible CI/CD and verified releases.

- 35+ public repositories — every project includes tests, CI, and release artifacts
- 58 downloadable Flutter games with verified builds across platforms
- Specialty: LLM cost control, multi-agent orchestration, durable workflows, and developer tooling

---

## Core strengths & impact areas

- System design for reliability: architect multi-component systems with clear boundaries, failure isolation, and audit trails.
- Cost-aware LLM operations: measure, attribute, and cap token spend; build tooling that prevents runaway bills.
- Deterministic testing & verification: test suites reflect real-world behaviour (live API verification where required).
- Observability & gating: actionable metrics, CIR / audit gates, and reproducible release processes.
- Developer experience: design systems, automation, and tooling that make teams faster and safer.

---

## Selected projects (high-impact, production-oriented)

| Project | Role & Impact |
|---|---|
| [horizon](https://github.com/Karthick-dev-cart/horizon) | Context-window budget manager for long-running agents — enforces token budgets by summarizing/dropping turns to keep sessions within limits. |
| [quorum](https://github.com/Karthick-dev-cart/quorum) | Multi-agent orchestration control plane with circuit breakers and per-agent failure isolation — designed for robust parallel workflows. |
| [pathfinder](https://github.com/Karthick-dev-cart/pathfinder) | Long-horizon task planner that detects drift and replans only remaining work to reduce wasted compute and operator overhead. |
| [waypoint](https://github.com/Karthick-dev-cart/waypoint) | Durable, checkpointed workflow engine with human-in-the-loop approval gates and full audit trails for compliance-sensitive flows. |
| [tokenledger](https://github.com/Karthick-dev-cart/tokenledger) | Double-entry style cost attribution for LLM calls — converts JSONL call logs into auditable cost reports for teams. |
| [oss-scout](https://github.com/Karthick-dev-cart/oss-scout) | Issue discovery & triage tooling that surfaces genuinely contributable issues, reducing noisy duplicates and improving onboarding. |

(Full repo list: https://github.com/Karthick-dev-cart?tab=repositories)

---

## Engineering approach

- Test-first: unit, integration, and system tests that codify expected behaviour and prevent regressions.
- Separation of concerns: business logic isolated from I/O and frameworks for easier reasoning and testing.
- Reproducible releases: binary/artifact verification, CI gates, and runbook-driven release steps.
- Defensive design: budget/circuit-breakers, per-call failure isolation, and robust fallbacks.
- Data-driven decisions: instrumentation and retroactive audits guide design and cost trade-offs.

---

## Technical toolkit

<p align="center">
  <img src="https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white" /> 
  <img src="https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" /> 
  <img src="https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=white" />
  <img src="https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/-Postgres-316192?style=flat-square&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/-Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/-Jest-99424f?style=flat-square&logo=jest&logoColor=white" />
</p>

---

## Verification & reproducibility

Every project is governed by the same release checklist:
1. Clean static analysis & linting (CI prevents merges with failing checks).
2. Tests that reflect real behaviour (system/integration tests against live or emulated backends when necessary).
3. Reproducible build artifacts (downloads or release packages for consumers).
4. Post-release verification (smoke or runtime checks to confirm the artifact actually runs).

---

## Notable patterns & libraries I build for teams

- Token spend auditing and anomaly detection (batch vs real-time routing, model arbitration).
- RAG pipeline tooling: query rewriting, chunking strategy benchmarks, retrieval comparators, and ground-checking.
- Agent observability: call-graph reconstruction, deterministic session replay, and per-step profiling.

---

## Speaking, mentoring & collaboration

I mentor engineers on system design, run architecture reviews focused on reliability and cost, and run workshops that translate ML/agent prototypes into production-ready systems. If you want help maturing an LLM workflow or making a release process robust, I’ll happily collaborate.

---

## GitHub metrics & quick links

[![Karthick's GitHub stats](https://github-readme-stats.vercel.app/api?username=Karthick-dev-cart&show_icons=true&theme=radical)](https://github.com/Karthick-dev-cart)  
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Karthick-dev-cart&layout=compact&theme=radical)](https://github.com/Karthick-dev-cart)

---

## Get in touch

- Open an issue or discussion on any repository — label it "collab" or "help wanted".  
- If you prefer private contact, tell me which contact method to include (email / LinkedIn / website) and I’ll add it.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=6E56CF&height=100&section=footer" alt="" width="100%" />
</p>
