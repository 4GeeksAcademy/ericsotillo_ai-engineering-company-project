# Progress: Nexova Solutions

Last updated: 2026-11-20

## Done

- Company briefing in [BRIEFING.md](../BRIEFING.md) (renamed from `CONTEXT.md`).
- Memory bank: [projectbrief.md](projectbrief.md) (business), [techContext.md](techContext.md) (technical context) and [progress.md](progress.md) (progress).
- Memory bank translated into English (source of truth); Spanish translation of the brief in [projectbrief.es.md](projectbrief.es.md).

## In progress

**Infrastructure for coding agents (Milestone 1)**, branch `feature/agent-memory-bank`: project memory, instructions, rules and skills for working with coding agents in the monorepo.

- Scope: agent documentation and configuration only. No applications are created in this iteration: no `uis/website`, no `uis/backoffice`, no code in `services/`.

## Next

1. Complete the current iteration:
   - `AGENTS.md`: memory files read at session start, pre-commit flow and protected files.
   - `.gitignore` with secrets and local files.
   - Rules in `.agents/rules/` and a skill in `.agents/skills/`.
   - Pull request to `main` and merge.
2. Upcoming iterations planned, according to [README.md](../README.md): Web, Programming, Backend, Telemetry, RAG (Retrieval-Augmented Generation), Agents, Workflows and Real time. The scope of each one will be defined when it starts.

## Problems / blockers

| Problem | Impact | When it gets resolved (planned) |
| --- | --- | --- |
| Empty `.gitignore` | A `.env` with secrets could be versioned | In the current iteration |
| `uv sync` fails in `post-create.sh`: there is no `pyproject.toml` | The devcontainer creation script stops at that step | When the first Python project (backend) is created |
| `@repo/shared-types`: `main` and `types` point to `index.ts`, but the file is at `types/index.ts` | Importing the package will fail | When the first app uses the package |

Briefing inconsistencies to be confirmed: see [projectbrief.md](projectbrief.md), section 6.
