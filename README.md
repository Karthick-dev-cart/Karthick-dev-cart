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

The throughline across these five: a hard budget or circuit breaker checked *before* work happens, failures isolated to the one call that raised them instead of taking the whole run down, and README sections that say plainly what's been verified against the real Claude API versus what's only proven against fakes.

| Project | What it does |
|---|---|
| [**horizon**](https://github.com/Karthick-dev-cart/horizon) | A context-window budget manager for long-running Claude agents: drops or summarizes old turns to stay within a token budget, never crashing on overflow |
| [**quorum**](https://github.com/Karthick-dev-cart/quorum) | A multi-agent orchestration control plane built around budget enforcement and per-agent failure isolation, not another happy-path demo framework |
| [**pathfinder**](https://github.com/Karthick-dev-cart/pathfinder) | A long-horizon task planner that detects when a plan has drifted from its goal and replans only the remaining work — the re-planning loop quorum's own README leaves as a known gap |
| [**waypoint**](https://github.com/Karthick-dev-cart/waypoint) | A durable, checkpointed workflow engine for chaining Claude-powered steps, with human-in-the-loop approval gates and an audit trail |
| [**rubric**](https://github.com/Karthick-dev-cart/rubric) | An LLM-as-judge eval harness that grades Claude outputs against rubric criteria using structured outputs, not regex on free text |

#### Design systems & frontend tooling

| Project | What it does |
|---|---|
| [**hearth-design-system**](https://github.com/Karthick-dev-cart/hearth-design-system) | Hearth — a Claude-inspired design system: tokens, accessible React components, and a written rulebook |

#### Developer tooling

| Project | What it does |
|---|---|
| [**oss-scout**](https://github.com/Karthick-dev-cart/oss-scout) | An MCP server that finds genuinely-contributable open source issues by filtering out ones already swarmed with duplicate PRs |
| [**flowforge**](https://github.com/Karthick-dev-cart/flowforge) | A small, config-driven, pluggable ETL pipeline toolkit |

#### Open source contributions

- [pandera#2415](https://github.com/unionai-oss/pandera/pull/2415) — fixed a regression where optional pydantic fields were incorrectly rejected as non-nullable. Found it the same way oss-scout now automates: searching for a genuine, unclaimed bug instead of a swarmed "good first issue."
