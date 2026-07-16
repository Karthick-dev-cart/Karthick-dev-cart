### Hi, I'm Karthick 👋

Senior technical architect and AI agentic automation engineer, working in **Python** — data pipelines, backend systems, and agent tooling. Also shipping **TypeScript** design systems and frontend tooling.

- 🔭 Building well-architected, fully-tested projects rather than one-off scripts — every repo below has a test suite, CI, and a README that explains *why*, not just *what*
- ⚙️ Focused on the unglamorous parts of AI agent systems: budget enforcement, per-call failure isolation, and honest verification against live APIs rather than mocks alone
- 🎨 Building thoughtful design systems with accessible React components and clear design tokens
- 🌱 Actively contributing real fixes to existing open source projects, not just building my own
- 💬 Ask me about Python architecture, ETL pipelines, agentic/MCP tooling, or design systems
- 📫 Reach me by opening an issue on any of my repos

#### Stack

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Pydantic](https://img.shields.io/badge/-Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)
![Pytest](https://img.shields.io/badge/-Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=white)
![Claude API](https://img.shields.io/badge/-Claude%20API-D97757?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)

#### Agent infrastructure

The throughline across these four: a hard budget or circuit breaker checked *before* work happens, failures isolated to the one call that raised them instead of taking the whole run down, and READ-THROUGH isolation so you never hallucinate about state nobody committed to shared storage.

| Project | What it does |
|---|---|
| [**horizon**](https://github.com/Karthick-dev-cart/horizon) | A context-window budget manager for long-running Claude agents: drops or summarizes old turns to stay within a token budget, never crashing on overflow |
| [**quorum**](https://github.com/Karthick-dev-cart/quorum) | A multi-agent orchestration control plane built around budget enforcement and failure isolation, not happy-path demos |
| [**waypoint**](https://github.com/Karthick-dev-cart/waypoint) | Per-call failure isolation and honest tool result verification for agentic systems |
| [**rubric**](https://github.com/Karthick-dev-cart/rubric) | Structured evaluation and scoring framework for agent outputs |

#### Design systems & frontend tooling

| Project | What it does |
|---|---|
| [**hearth-design-system**](https://github.com/Karthick-dev-cart/hearth-design-system) | Hearth — a Claude-inspired design system: tokens, accessible React components, and a written rulebook |

#### Developer tooling

| Project | What it does |
|---|---|
| [**oss-scout**](https://github.com/Karthick-dev-cart/oss-scout) | Discovers and validates patterns in open source projects, helping identify architecture decisions and integration points |
| [**flowforge**](https://github.com/Karthick-dev-cart/flowforge) | Workflow automation and orchestration primitives for building resilient data pipelines |

#### Open source contributions

- [pandera#2415](https://github.com/unionai-oss/pandera/pull/2415) — fixed a regression where optional pydantic fields were incorrectly rejected as non-nullable. Found it the same way oss-scout does: systematic crawl of type narrowing logic
