# GitHub Agentic AI Developer — Study Notes

Personal study companion for the **GitHub Agentic AI Developer** course.
Each module gets a self-contained web page with unit summaries and an interactive
multiple-choice quiz.

## Modules

| # | Module | Page | Source |
|---|--------|------|--------|
| 01 | Foundations of Agentic AI in GitHub | [index.html](index.html) | [Microsoft Learn](https://learn.microsoft.com/en-gb/training/modules/foundations-agentic-ai/) |
| 02 | Designing Agent Architecture & SDLC Integration | [module-02.html](module-02.html) | [Microsoft Learn](https://learn.microsoft.com/en-gb/training/modules/design-agent-architecture-integration/) |
| 03 | Tooling, MCP & Agent Execution Environments | [module-03.html](module-03.html) | [Microsoft Learn](https://learn.microsoft.com/en-gb/training/modules/agent-tooling-mcp-execution-environments/) |

## Study system

Each module page follows a three-step, evidence-based revision flow:

1. **Read** — condensed unit summaries with the module's key tables and diagrams.
2. **Free recall** — a brain-dump box *before* the quiz, with a self-check list of key
   points (retrieval practice beats re-reading).
3. **Spaced-repetition flashcards** — Leitner-style deck (Again / Good / Easy);
   cards return at 1 → 3 → 7 → 14 day intervals. Progress persists in `localStorage`.
4. **Quiz** — 10 questions drawn from a larger shuffled bank, with shuffled options,
   instant explanations, and a persisted best score.

Future module quizzes should interleave 2–3 questions from earlier modules.

## Usage

Open `index.html` in a browser — no build step, no dependencies (fonts load from Google Fonts).
Recall dumps, flashcard scheduling, and best scores are stored per-browser in `localStorage`.

```sh
open index.html
```
