<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=6E56CF&height=150&section=header" alt="" width="100%" />
</p>

### Hi, I'm Karthick 👋

**35+ repos, every one shipped with a real test suite and CI · verified against live APIs, not mocks alone · also shipping 58 downloadable, verified Flutter games**

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Karthick-dev-cart&color=6e56cf&style=flat-square&label=profile+views" alt="Profile views" />
  <img src="https://img.shields.io/badge/games%20shipped-58-6e56cf?style=flat-square" alt="Games shipped" />
  <img src="https://img.shields.io/badge/agent%20infra%20tools-5-6e56cf?style=flat-square" alt="Agent infra tools" />
  <img src="https://img.shields.io/badge/token%20economics%20tools-8-6e56cf?style=flat-square" alt="Token economics tools" />
  <img src="https://img.shields.io/badge/RAG%20pipeline%20tools-7-6e56cf?style=flat-square" alt="RAG pipeline tools" />
  <img src="https://img.shields.io/badge/claude%20workflow%20tools-6-6e56cf?style=flat-square" alt="Claude workflow tools" />
  <img src="https://img.shields.io/badge/dev%20tooling-2-6e56cf?style=flat-square" alt="Dev tooling" />
  <img src="https://img.shields.io/badge/game%20releases-Windows%20%7C%20Android-6e56cf?style=flat-square" alt="Release platforms" />
</p>

Senior technical architect and AI agentic automation engineer, working in **Python** — data pipelines, backend systems, and agent tooling. Also shipping **TypeScript** design systems and frontend tooling.

- 🔭 Building well-architected, fully-tested projects rather than one-off scripts — every repo below has a test suite, CI, and a README that explains *why*, not just *what*
- ⚙️ Focused on the unglamorous parts of AI agent systems: budget enforcement, per-call failure isolation, and honest verification against live APIs rather than mocks alone
- 🎨 Building thoughtful design systems with accessible React components and clear design tokens
- 🌱 Actively contributing real fixes to existing open source projects, not just building my own
- 💬 Ask me about Python architecture, ETL pipelines, agentic/MCP tooling, or design systems
- 📫 Reach me by opening an issue on any of my repos

#### Stack

<p align="center">
  <img src="https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/-Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white" alt="Pydantic" />
  <img src="https://img.shields.io/badge/-Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="Pytest" />
  <img src="https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=white" alt="React" />
  <img src="https://img.shields.io/badge/-Claude%20API-D97757?style=flat-square" alt="Claude API" />
  <img src="https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/-Flutter-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter" />
  <img src="https://img.shields.io/badge/-Dart-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dart" />
</p>

<p align="center">
  <img height="165em" src="https://streak-stats.demolab.com?user=Karthick-dev-cart&theme=tokyonight&hide_border=true&background=00000000&disable_animations=true" alt="GitHub streak stats" />
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Karthick-dev-cart/Karthick-dev-cart/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Karthick-dev-cart/Karthick-dev-cart/output/github-contribution-grid-snake.svg" />
    <img alt="A snake animation eating through my GitHub contribution graph" src="https://raw.githubusercontent.com/Karthick-dev-cart/Karthick-dev-cart/output/github-contribution-grid-snake.svg" width="100%" />
  </picture>
</p>

#### How I verify before shipping

Same checklist on every repo below, whether it's a Python agent tool or a Flutter game — this is the actual gate, not aspirational:

1. **Logic and interface are separate.** Business/game logic lives in its own module with zero framework imports — no Flutter widgets in a game's rules, no HTTP client in an agent's planning loop — so it's unit-testable without spinning up a UI or hitting a live API.
2. **Test depth matches the actual complexity**, not a padded-to-look-thorough number. An exhaustive-search AI gets an exhaustive test that plays out every opponent line; a heuristic AI gets concrete tactical positions; a puzzle generator gets a correctness proof (uniqueness, solvability, or connectivity — whichever invariant is load-bearing); a card game gets its actual rulebook exercised edge case by edge case.
3. **Static analysis has to be clean** — `flutter analyze` / linting with zero issues — before anything moves on.
4. **It has to actually run**, not just build. For the Flutter games specifically, that means launching the real Windows `.exe` and confirming the process is alive via a live process check, because a successful compile and a working app are not the same claim.
5. **Downloadable, not just readable, on more than one platform.** Each game repo ships as a ready-to-run [GitHub Release](https://github.com/Karthick-dev-cart?tab=repositories) — a Windows `.exe` bundle *and* an Android `.apk` on the same tag — no Flutter SDK, no build step, just download and run.

#### Field notes

A few specific things that came up doing the above, because "it works" is worth backing with what actually happened rather than asserted on faith:

- **A cross-drive Kotlin bug, caught on one repo before it could waste 57 identical failures.** Building the first Android release, `flutter build apk --release` ran for **19 minutes and 36 seconds** before failing with `IllegalArgumentException: this and base files have different roots`. Root cause: Kotlin's incremental-compilation cache tries to compute a relative path between the project directory (`D:\Games\...`) and the Flutter pub-cache (`C:\Users\...`) — which is undefined on Windows once two paths don't share a drive letter. Fix was one line (`kotlin.incremental=false` in `android/gradle.properties`). The important part isn't the line, it's the sequencing: piloted the fix on a single repo, confirmed the rebuild succeeded in **102 seconds**, verified the resulting APK actually uploaded and matched what a clean install expects — *then* rolled the fix out to all 58 projects. Discovering that bug 58 times, mid-rollout, would have cost hours instead of one extra pilot run.
- **A silent Firebase gap, caught by checking for the file instead of assuming.** One game (`brain_quest`) uses Firebase email/password auth. Before shipping it as a release on any platform, checking for `firebase_options.dart` and `android/app/google-services.json` turned up neither — the Firebase *packages* were wired in, but the project was never actually connected to a live Firebase project. That's not a platform limitation to route around, it's a broken build waiting to happen, so it's excluded from both the Windows and Android release rollouts until it's properly configured, rather than shipped anyway and left for someone to discover by downloading it.
- **Windows builds are verified by launching them, not by trusting exit code 0.** Every game's `.exe` is confirmed alive afterward via a live process check, because a Flutter Windows release can compile clean and still fail to start if a plugin's native dependencies aren't bundled correctly — "the build finished" and "the app runs" are different claims, and only the second one is the one that matters.

#### Agent infrastructure

The throughline across these five: a hard budget or circuit breaker checked *before* work happens, failures isolated to the one call that raised them instead of taking the whole run down, and README sections that say plainly what's been verified against the real Claude API versus what's only proven against fakes.

| Project | What it does |
|---|---|
| [**horizon**](https://github.com/Karthick-dev-cart/horizon) | A context-window budget manager for long-running Claude agents: drops or summarizes old turns to stay within a token budget, never crashing on overflow |
| [**quorum**](https://github.com/Karthick-dev-cart/quorum) | A multi-agent orchestration control plane built around budget enforcement and per-agent failure isolation, not another happy-path demo framework |
| [**pathfinder**](https://github.com/Karthick-dev-cart/pathfinder) | A long-horizon task planner that detects when a plan has drifted from its goal and replans only the remaining work — the re-planning loop quorum's own README leaves as a known gap |
| [**waypoint**](https://github.com/Karthick-dev-cart/waypoint) | A durable, checkpointed workflow engine for chaining Claude-powered steps, with human-in-the-loop approval gates and an audit trail |
| [**rubric**](https://github.com/Karthick-dev-cart/rubric) | An LLM-as-judge eval harness that grades Claude outputs against rubric criteria using structured outputs, not regex on free text |

#### LLM token economics

Cost-side tooling for running LLMs at scale — attribution, anomaly detection, cross-provider pricing, and the batch/fine-tuning tradeoffs teams actually have to decide on. Every tool below states in its own README exactly how it differs from its closest sibling here, since several answer adjacent-sounding cost questions.

| Project | What it does |
|---|---|
| [**tokenledger**](https://github.com/Karthick-dev-cart/tokenledger) | An offline, double-entry-style cost-attribution ledger: turns a JSONL log of LLM calls into a report of which project/feature/user actually drove spend |
| [**spend-sentinel**](https://github.com/Karthick-dev-cart/spend-sentinel) | A statistical billing-anomaly detector — robust median/MAD baselines per project/feature/user, not a fixed threshold that breaks the first time usage grows |
| [**model-arbitrage**](https://github.com/Karthick-dev-cart/model-arbitrage) | A cross-provider pricing comparator that recomputes the full cost ranking from your actual workload shape — cache-hit rate alone can flip which model is cheapest |
| [**batch-economics**](https://github.com/Karthick-dev-cart/batch-economics) | Decides whether a workload should run real-time or on a discounted batch API, gated on whether your latency SLA can tolerate the turnaround |
| [**finetune-vs-prompt**](https://github.com/Karthick-dev-cart/finetune-vs-prompt) | Computes the request-volume breakeven where fine-tuning's training cost pays for itself against long-context prompting — and says plainly when it never does |
| [**pareto-router**](https://github.com/Karthick-dev-cart/pareto-router) | Finds the Pareto-optimal cost/quality frontier in a historical log of real request outcomes — audits what already happened, not a live router |
| [**cache-yield**](https://github.com/Karthick-dev-cart/cache-yield) | Estimates how much prompt caching would have saved on a historical request log, from real shared-prefix structure and real cache pricing multipliers |
| [**tokendiff**](https://github.com/Karthick-dev-cart/tokendiff) | A CI gate that fails the build when a prompt template's token count regresses past a configurable threshold |

#### RAG pipeline tooling

Five tools spanning one RAG pipeline end to end — rewrite the query, chunk the corpus, retrieve, pack the context window, then check the generated answer stayed grounded — plus two supporting tools for cost planning and index staleness. Each README documents exactly where it sits in that pipeline and what its neighbors don't do.

| Project | What it does |
|---|---|
| [**query-rewriter-bench**](https://github.com/Karthick-dev-cart/query-rewriter-bench) | Benchmarks query-rewriting strategies upstream of retrieval — does expanding/decomposing the query actually improve what gets retrieved? |
| [**chunk-bench**](https://github.com/Karthick-dev-cart/chunk-bench) | Benchmarks chunking strategies by their effect on retrieval quality, holding the embedder fixed |
| [**retrieval-arena**](https://github.com/Karthick-dev-cart/retrieval-arena) | Benchmarks sparse (BM25), dense, and hybrid (RRF) retrieval methods against the same corpus and eval set |
| [**context-packer**](https://github.com/Karthick-dev-cart/context-packer) | Solves the downstream knapsack problem: which already-scored chunks actually fit a context-token budget |
| [**groundcheck**](https://github.com/Karthick-dev-cart/groundcheck) | Checks whether a generated answer stayed faithful to its retrieved context, sentence by sentence |
| [**rag-costmap**](https://github.com/Karthick-dev-cart/rag-costmap) | Projects a RAG system's indexing and recurring query/storage costs from 10K to 10M documents, before you build it |
| [**index-decay**](https://github.com/Karthick-dev-cart/index-decay) | Watches a RAG vector index's source documents for drift and tells you exactly what needs re-embedding |

#### Claude agent/workflow tooling

Observability and correctness tooling for multi-step Claude agent workflows — three transcript-analysis tools (call graph, replay/diff, flame-graph profile) each scoped to a different question, plus schema-drift detection, behavioral regression testing, and adversarial red-teaming.

| Project | What it does |
|---|---|
| [**agent-graph**](https://github.com/Karthick-dev-cart/agent-graph) | Reconstructs a multi-agent session's call tree from its transcript — structure, cost, and where the tokens went |
| [**session-replay**](https://github.com/Karthick-dev-cart/session-replay) | Deterministically steps through a session transcript and diffs two runs of "the same" task to find exactly where they diverged |
| [**workflow-profiler**](https://github.com/Karthick-dev-cart/workflow-profiler) | A per-step flame-graph profiler for where time and cost actually went in an agentic workflow |
| [**tool-contract**](https://github.com/Karthick-dev-cart/tool-contract) | Statically detects drift between a declared MCP/tool-use JSON Schema and the model's actual observed calls |
| [**prompt-regress**](https://github.com/Karthick-dev-cart/prompt-regress) | Records a baseline against the live model, then flags semantic drift and format breaks after a prompt/model change |
| [**guardrail-bench**](https://github.com/Karthick-dev-cart/guardrail-bench) | Adversarial red-teaming harness that scores a system prompt's robustness against jailbreak/injection/extraction probes |

#### Design systems & frontend tooling

| Project | What it does |
|---|---|
| [**hearth-design-system**](https://github.com/Karthick-dev-cart/hearth-design-system) | Hearth — a Claude-inspired design system: tokens, accessible React components, and a written rulebook |

#### Games

**58** small Flutter games, each its own repo, each shipped as source *and* as a downloadable build under that repo's Releases tab — a Windows `.exe` and an Android `.apk` on the same `v1.0.0` tag. See [How I verify before shipping](#how-i-verify-before-shipping) and [Field notes](#field-notes) above for the pipeline every one of them goes through, including the one that shipped Windows-only for a documented reason.

<details>
<summary><strong>🧠 Where the AI actually thinks</strong> — exhaustive proofs, minimax, and pathfinding</summary>
<br>

| Project | What it does |
|---|---|
| [**chess**](https://github.com/Karthick-dev-cart/chess) | Minimax + alpha-beta AI, but the real story is the move generator: verified with [perft](https://www.chessprogramming.org/Perft_Results) against published reference values across three positions, because start-position perft alone never even reaches castling or promotion |
| [**tictactoe**](https://github.com/Karthick-dev-cart/tictactoe) | An actually-unbeatable AI — full minimax verified by an exhaustive test that plays it against every possible opponent line, not a couple of hand-picked cases |
| [**nim**](https://github.com/Karthick-dev-cart/nim) | AI plays the mathematically perfect nim-sum strategy from combinatorial game theory, not a heuristic — verified against every possible opponent reply, not just spot-checked |
| [**connectfour**](https://github.com/Karthick-dev-cart/connectfour) | Minimax + alpha-beta with a window-counting heuristic, tested against concrete tactical positions (winning drops, blocked threats) rather than just "does it run" |
| [**checkers**](https://github.com/Karthick-dev-cart/checkers) | Mandatory captures and multi-jump chains — the two rules a simplified checkers implementation usually drops — verified with a constructed double-jump position, not just single captures |
| [**pixelchase**](https://github.com/Karthick-dev-cart/pixelchase) | Pac-Man-style ghosts that recompute a fresh BFS shortest path to the player *every tick* (not a path frozen at spawn), and flee toward the farthest open cell once you've eaten a power pellet |
| [**lightcycles**](https://github.com/Karthick-dev-cart/lightcycles) | A Tron-style AI that doesn't chase you at all — it flood-fills the open space behind each candidate move and picks whichever leaves it the most room to keep riding |

</details>

<details>
<summary><strong>🔍 Where correctness is the whole point</strong> — generators, physics, and rules</summary>
<br>

| Project | What it does |
|---|---|
| [**sudoku**](https://github.com/Karthick-dev-cart/sudoku) | A real backtracking generator that guarantees a unique solution — not naive fill-then-remove, which can silently ship ambiguous puzzles |
| [**fifteenpuzzle**](https://github.com/Karthick-dev-cart/fifteenpuzzle) | Generates only solvable boards using the actual parity invariant that governs the 15-puzzle — verified against the historically famous "14-15 swap," the real-world proof case for why the invariant matters |
| [**freecell**](https://github.com/Karthick-dev-cart/freecell) | Full Freecell rules, not a simplified card game — moving one card at a time through free cells *is* how Freecell actually works, unlike the single-card-move scope-cut in the Klondike build |
| [**dotsandboxes**](https://github.com/Karthick-dev-cart/dotsandboxes) | Handles a single line completing two boxes at once (a shared edge), with an AI that specifically avoids gifting the opponent a free box |
| [**wordle**](https://github.com/Karthick-dev-cart/wordle) | Duplicate-letter-aware color feedback (unit tested) and a persisted win streak |
| [**brain_quest**](https://github.com/Karthick-dev-cart/brain_quest) | Four brain-training mini-games behind Firebase email/password sign-in — currently source-only, no release build, until its Firebase project connection is finished (see [Field notes](#field-notes)) |

</details>

<details>
<summary><strong>🕹️ The rest of the collection</strong> — 45 more, same rigor, one tap away</summary>
<br>

Minesweeper, Battleship, Hangman, Rock Paper Scissors, Whack-a-Mole, Simon Says, Yahtzee, Boggle, Mastermind, Reversi, Mancala, Lights Out, Tetris, Bubble Shooter, Match 3, Air Hockey, Gomoku, Ultimate Tic-Tac-Toe, Tower of Hanoi, Peg Solitaire, Go Fish, Crazy Eights, Solitaire, Blackjack, War, Word Search, Anagram, Math Quiz Sprint, Typing Speed Test, 2048, Breakout, Pong, Asteroids, Doodle Jumper, Maze Runner, Memory Match, Space Invaders, Flood Fill, Threes Merge, Balloon Pop, Fruit Slice, Mini Crossword, Trivia Quiz, SkyHop, Snake — and counting.

Full list, always current, on the [repositories page](https://github.com/Karthick-dev-cart?tab=repositories).

</details>

#### Developer tooling

| Project | What it does |
|---|---|
| [**oss-scout**](https://github.com/Karthick-dev-cart/oss-scout) | An MCP server that finds genuinely-contributable open source issues by filtering out ones already swarmed with duplicate PRs |
| [**flowforge**](https://github.com/Karthick-dev-cart/flowforge) | A small, config-driven, pluggable ETL pipeline toolkit |

#### Open source contributions

- [pandera#2415](https://github.com/unionai-oss/pandera/pull/2415) — fixed a regression where optional pydantic fields were incorrectly rejected as non-nullable. Found it the same way oss-scout now automates: searching for a genuine, unclaimed bug instead of a swarmed "good first issue."

#### In progress

- [google/langextract](https://github.com/google/langextract) — verified two genuine, unclaimed bugs against current `main`: [#492](https://github.com/google/langextract/issues/492) (OpenAI o-series/gpt-3.5 model IDs route to no provider) and [#491](https://github.com/google/langextract/issues/491) (a refused/content-filtered OpenAI completion is silently reported as a successful empty result instead of raising, unlike the equivalent batch-path guard). Fixes and regression tests are ready; PRs are pending because the repo's contribution guidelines require the linked issue to have community reactions first — commented on both to help clear that bar honestly rather than opening PRs against a 0-reaction issue.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=6E56CF&height=100&section=footer" alt="" width="100%" />
</p>
