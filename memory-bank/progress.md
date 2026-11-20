# Progress: Nexova Solutions

Last updated: 2026-11-20

## Done

**Infrastructure for coding agents (Milestone 1)**: completed.

- Company briefing in [BRIEFING.md](../BRIEFING.md) (renamed from `CONTEXT.md`).
- Memory bank: [projectbrief.md](projectbrief.md) (business), [techContext.md](techContext.md) (technical context) and [progress.md](progress.md) (progress).
- Memory bank translated into English (source of truth); Spanish translation of the brief in [projectbrief.es.md](projectbrief.es.md).
- Agent instructions in [AGENTS.md](../AGENTS.md) (session start, language, pre-commit flow, protected paths, stop and ask); Spanish translation in [AGENTS.es.md](../AGENTS.es.md).
- [.gitignore](../.gitignore) for secrets (`.env`), Python, Node, logs and OS files.
- First agent rule: [docs-style](../.agents/rules/docs-style.md), auto-attached to Markdown files.
- First agent skill: [update-memory-bank](../.agents/skills/update-memory-bank/SKILL.md), indexed in [AGENTS.md](../AGENTS.md) and used in pre-commit step 5.

## In progress

None. The next iteration has not started.

## Next

- Upcoming iterations planned, according to [README.md](../README.md): Web, Programming, Backend, Telemetry, RAG (Retrieval-Augmented Generation), Agents, Workflows and Real time. The scope of each one will be defined when it starts.

## Problems / blockers

| Problem | Impact | When it gets resolved (planned) |
| --- | --- | --- |
| `uv sync` fails in `post-create.sh`: there is no `pyproject.toml` | The devcontainer creation script stops at that step | When the first Python project (backend) is created |
| `@repo/shared-types`: `main` and `types` point to `index.ts`, but the file is at `types/index.ts` | Importing the package will fail | When the first app uses the package |

Briefing inconsistencies to be confirmed: see [projectbrief.md](projectbrief.md), section 6.
