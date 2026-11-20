# AGENTS.md

## Project

Nexova Solutions is a human resources and talent selection consultancy (Valencia and Miami) that needs automation, data and AI tools to operate at scale. This monorepo holds its applications, AI agents, skills and workflows. Business context: [memory-bank/projectbrief.md](memory-bank/projectbrief.md); full briefing: [BRIEFING.md](BRIEFING.md).

## Session start

Read, in this order:

1. [memory-bank/projectbrief.md](memory-bank/projectbrief.md): business, goals and constraints.
2. [memory-bank/techContext.md](memory-bank/techContext.md): stack, layer map, decisions and open questions.
3. [memory-bank/progress.md](memory-bank/progress.md): what is done, in progress and next.
4. The rules in `.agents/rules/` that apply to the task.
5. The README of the folder you will work in.

Read [BRIEFING.md](BRIEFING.md) only when you need the detail of an area, not in every session.

## Language

- Read and update only the English files. The `.es.md` files are translations for people.
- If you change a file that has a `.es.md` translation, update the translation in the same commit.

## Where things go

- Application layer: public website in `uis/website`, internal app in `uis/backoffice`, APIs in `services/`. Create them only when a task asks for it.
- Before creating a file, check [techContext.md › Application layer map](memory-bank/techContext.md#4-application-layer-map) for the folder it belongs in.
- `.agents/` is the coding agent's configuration (rules, skills). `agents/` and `skills/` are Nexova's AI product. Do not mix them.
- Do not create parallel trees: if a folder already exists for something, use it.

## Pre-commit flow

Run every step before each commit and check its verification.

1. **Branch**: `git branch --show-current` is not `main`.
2. **Scope**: `git diff --staged --name-only` lists only files of the task; any protected path requires explicit developer confirmation.
3. **Security**: no `.env` file in that list; no keys, tokens or passwords in `git diff --staged`; sample data is fictitious.
4. **Validation**: paths and links cited in docs exist; tests and lint of affected folders pass (when they exist).
5. **Memory**: when the commit completes, starts or blocks a task, `memory-bank/progress.md` is in the staged list with today's date in "Last updated"; `memory-bank/techContext.md` too if a technical decision was made.
6. **Commit**: Conventional Commits message (`type(scope): description`), one logical unit per commit, no tool co-author lines.

If any step fails, stop and tell the developer. Do not commit.

## Delivery

1. Work on a `<type>/<short-name>` branch, never on `main`. Types: `feature/` (for `feat` commits), `fix/`, `docs/`, `chore/`.
2. Push only your working branch and open a pull request to the branch it was created from (usually `main`).
3. A developer reviews and merges it. Never push to or merge into any other branch yourself.

## Protected paths

Do not modify without explicit developer confirmation.

- **Sources of truth**: `BRIEFING.md`, `BRIEFING.es.md`, `company-choice.md`, `memory-bank/projectbrief.md`, `memory-bank/projectbrief.es.md`.
- **Agent configuration**: `AGENTS.md`, `AGENTS.es.md`, `.agents/`.
- **Infrastructure and shared code**: `.devcontainer/`, `packages/shared/`, `.gitignore`.
- **Template READMEs**: `README.md`, `README.es.md` and each folder's README.

## Stop and ask

Ask the developer before you:

- create a top-level folder;
- add a dependency;
- decide anything listed in [techContext.md › To be decided](memory-bank/techContext.md#7-to-be-decided);
- delete files;
- touch a protected path;
- continue with a requirement that is ambiguous or contradicts the briefing.
