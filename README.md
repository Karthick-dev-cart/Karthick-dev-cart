### Hi, I'm Karthick 👋

![Profile views](https://komarev.com/ghpvc/?username=Karthick-dev-cart&color=6e56cf&style=flat-square&label=profile+views)
![Games shipped](https://img.shields.io/badge/games%20shipped-58-6e56cf?style=flat-square)
![Agent infra tools](https://img.shields.io/badge/agent%20infra%20tools-5-6e56cf?style=flat-square)
![Dev tooling](https://img.shields.io/badge/dev%20tooling-2-6e56cf?style=flat-square)

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
![Flutter](https://img.shields.io/badge/-Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/-Dart-0175C2?style=flat-square&logo=dart&logoColor=white)

<p align="left">
  <img height="165em" src="https://github-readme-stats.vercel.app/api?username=Karthick-dev-cart&show_icons=true&count_private=true&theme=tokyonight&hide_border=true&hide_title=true" alt="GitHub stats" />
  <img height="165em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Karthick-dev-cart&layout=compact&theme=tokyonight&hide_border=true&hide_title=true" alt="Top languages" />
</p>

#### How I verify before shipping

Same checklist on every repo below, whether it's a Python agent tool or a Flutter game — this is the actual gate, not aspirational:

1. **Logic and interface are separate.** Business/game logic lives in its own module with zero framework imports — no Flutter widgets in a game's rules, no HTTP client in an agent's planning loop — so it's unit-testable without spinning up a UI or hitting a live API.
2. **Test depth matches the actual complexity**, not a padded-to-look-thorough number. An exhaustive-search AI gets an exhaustive test that plays out every opponent line; a heuristic AI gets concrete tactical positions; a puzzle generator gets a correctness proof (uniqueness, solvability, or connectivity — whichever invariant is load-bearing); a card game gets its actual rulebook exercised edge case by edge case.
3. **Static analysis has to be clean** — `flutter analyze` / linting with zero issues — before anything moves on.
4. **It has to actually run**, not just build. For the Flutter games specifically, that means launching the real Windows `.exe` and confirming the process is alive via a live process check, because a successful compile and a working app are not the same claim.
5. **Downloadable, not just readable.** Each game repo ships a ready-to-run Windows build as a [GitHub Release](https://github.com/Karthick-dev-cart?tab=repositories) — no Flutter SDK required, just download, unzip, and run.

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

#### Games

**58** small Flutter games, each its own repo, each shipped as source *and* as a downloadable Windows `.exe` under that repo's Releases tab — see [How I verify before shipping](#how-i-verify-before-shipping) above for the pipeline every one of them goes through.

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
| [**brain_quest**](https://github.com/Karthick-dev-cart/brain_quest) | Four brain-training mini-games behind Firebase email/password sign-in |

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
