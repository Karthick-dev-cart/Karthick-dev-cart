### Hi, I'm Karthick 👋

Senior technical architect and AI agentic automation engineer, working in **Python** — data pipelines, backend systems, and agent tooling.

- 🔭 Building well-architected, fully-tested projects rather than one-off scripts — every repo below has a test suite, CI, and a README that explains *why*, not just *what*
- ⚙️ Focused on the unglamorous parts of AI agent systems: budget enforcement, per-call failure isolation, and honest verification against live APIs rather than mocks alone
- 🌱 Actively contributing real fixes to existing open source projects, not just building my own
- 💬 Ask me about Python architecture, ETL pipelines, or agentic/MCP tooling
- 📫 Reach me by opening an issue on any of my repos

#### Stack

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pydantic](https://img.shields.io/badge/-Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)
![Pytest](https://img.shields.io/badge/-Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Claude API](https://img.shields.io/badge/-Claude%20API-D97757?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)

#### Agent infrastructure

The throughline across these four: a hard budget or circuit breaker checked *before* work happens, failures isolated to the one call that raised them instead of taking the whole run down, and README sections that say plainly what's been verified against the real Claude API versus what's only proven against fakes.

| Project | CI | What it does |
|---|---|---|
| [**horizon**](https://github.com/Karthick-dev-cart/horizon) | [![CI](https://img.shields.io/github/actions/workflow/status/Karthick-dev-cart/horizon/ci.yml?branch=main&style=flat-square&label=)](https://github.com/Karthick-dev-cart/horizon/actions) | A context-window budget manager for long-running Claude agents — drops or summarizes old turns to stay within a token budget, never crashing on overflow |
| [**quorum**](https://github.com/Karthick-dev-cart/quorum) | [![CI](https://img.shields.io/github/actions/workflow/status/Karthick-dev-cart/quorum/ci.yml?branch=main&style=flat-square&label=)](https://github.com/Karthick-dev-cart/quorum/actions) | A multi-agent orchestration control plane built around budget enforcement and per-agent failure isolation, not another happy-path demo framework |
| [**waypoint**](https://github.com/Karthick-dev-cart/waypoint) | [![CI](https://img.shields.io/github/actions/workflow/status/Karthick-dev-cart/waypoint/ci.yml?branch=main&style=flat-square&label=)](https://github.com/Karthick-dev-cart/waypoint/actions) | A durable, checkpointed workflow engine for chaining Claude-powered steps, with human-in-the-loop approval gates and an audit trail |
| [**rubric**](https://github.com/Karthick-dev-cart/rubric) | [![CI](https://img.shields.io/github/actions/workflow/status/Karthick-dev-cart/rubric/ci.yml?branch=main&style=flat-square&label=)](https://github.com/Karthick-dev-cart/rubric/actions) | An LLM-as-judge eval harness that grades Claude outputs against rubric criteria using structured outputs, not regex on free text |

#### Tooling

| Project | CI | What it does |
|---|---|---|
| [**oss-scout**](https://github.com/Karthick-dev-cart/oss-scout) | [![CI](https://img.shields.io/github/actions/workflow/status/Karthick-dev-cart/oss-scout/ci.yml?branch=main&style=flat-square&label=)](https://github.com/Karthick-dev-cart/oss-scout/actions) | An MCP server that finds genuinely-contributable open source issues by filtering out ones already swarmed with duplicate PRs |
| [**flowforge**](https://github.com/Karthick-dev-cart/flowforge) | [![CI](https://img.shields.io/github/actions/workflow/status/Karthick-dev-cart/flowforge/ci.yml?branch=main&style=flat-square&label=)](https://github.com/Karthick-dev-cart/flowforge/actions) | A small, config-driven, pluggable ETL pipeline toolkit |

#### Open source contributions

- [pandera#2415](https://github.com/unionai-oss/pandera/pull/2415) — fixed a regression where optional pydantic fields were incorrectly rejected as non-nullable. Found it the same way oss-scout now automates: searching for a genuine, unclaimed bug instead of a swarmed "good first issue."
