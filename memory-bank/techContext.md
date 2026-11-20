# Tech context: Nexova Solutions

Technical context of the monorepo. The business is in [projectbrief.md](projectbrief.md).

Labels: **Exists** · **Template suggestion** · **To be confirmed**. Section 1 describes Nexova's systems, not the repository's: it only cites its source.

## 1. Nexova's current systems

Source: [BRIEFING.md](../BRIEFING.md) › How the company is organised and › Technology and Infrastructure.

- Tools: HubSpot as CRM (Customer Relationship Management), legacy Zendesk, a home-built ATS (Applicant Tracking System) from the 2010s, Google Workspace and spreadsheets.
- Corporate Training with PDF, Google Form and spreadsheet; Human Resources with email and spreadsheets; management with a weekly PDF report made by hand.
- Gaps: disconnected tools; no telemetry or centralised logging; failures are detected by users; manual deployments; support without a knowledge base or real-time visibility.

## 2. Development environment

Sources: [devcontainer.json](../.devcontainer/devcontainer.json), [post-create.sh](../.devcontainer/post-create.sh), [README.md](../README.md) › How to start.

- **Exists**: Codespaces-ready devcontainer, image `devcontainers/universal:2`, user `codespace`, host Docker socket mounted.
- **Exists**: forwarded ports 3000, 8000 and 5678. **To be confirmed**: no file documents what each one is for.
- **Exists**: `post-create.sh` enables Corepack and `pnpm@latest`, installs `uv` and runs `uv sync`.
- **To be confirmed**: `uv sync` needs a `pyproject.toml` and the repository has none.

## 3. Monorepo stack

| Item                                  | Label                                      | Source                                                                                                                      |
| ------------------------------------- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Python                                | Exists                                     | [devcontainer.json](../.devcontainer/devcontainer.json), [pandas_clean.py](../skills/data-analysis/scripts/pandas_clean.py) |
| TypeScript                            | Exists                                     | [index.ts](../packages/shared/types/index.ts)                                                                               |
| uv (Python manager)                   | Exists (installed)                         | [post-create.sh](../.devcontainer/post-create.sh)                                                                           |
| pnpm (JavaScript/TypeScript manager)  | Exists (installed); no root workspace      | [post-create.sh](../.devcontainer/post-create.sh); [README.md](../README.md) › Current status of the template               |
| `@repo/shared-types`                  | Exists                                     | [package.json](../packages/shared/package.json)                                                                             |
| FastAPI, n8n                          | Template suggestion                        | [README.md](../README.md) › services/, › workflows/                                                                         |
| `docker-compose.yml`                  | Template suggestion (does not exist)       | [README.md](../README.md) › Root files                                                                                      |

**To be confirmed**: `main` and `types` in `@repo/shared-types` point to `index.ts`, but the file is at `types/index.ts`.

## 4. Application layer map

Source: [README.md](../README.md) › Folder guide and the actual contents of the repository.

| Path             | What goes there                                     | Status                                                     |
| ---------------- | --------------------------------------------------- | ---------------------------------------------------------- |
| `uis/website`    | Public website                                      | not created                                                |
| `uis/backoffice` | Internal administration application                 | not created                                                |
| `services/`      | APIs and workers                                     | template README only                                       |
| `agents/`        | One agent per subfolder                             | exists (only template `_template/` and `tools/`)           |
| `skills/`        | Reusable skills (`SKILL.md` and scripts)            | exists (`_template/`, `data-analysis/` and empty folders)  |
| `mcps/`          | MCP (Model Context Protocol) servers                | template README only                                       |
| `workflows/`     | Automations and orchestration                       | template README only                                       |
| `.agents/`       | Coding agent configuration (rules, skills)          | not created                                                |

Note: `skills/` (template) is for skills of Nexova's AI product; the coding agent's skills go in `.agents/skills/`.

## 5. Architecture decisions

- **Briefing renamed from `CONTEXT.md` to `BRIEFING.md` (and `BRIEFING.es.md`)** · Project requirement: `BRIEFING.md` at the root · 2026-11-17 (commit e1ecfd0).
- **Naming convention**: kebab-case for new files (rules, skills, docs); snake_case for Python code (PEP 8); UPPERCASE for root meta files (`README.md`, `AGENTS.md`, `BRIEFING.md`). Spanish translations use the `.es.md` suffix (`BRIEFING.es.md`, `projectbrief.es.md`). Exception: the memory bank keeps its canonical names (`projectbrief.md`, `techContext.md`, `progress.md`) · Each convention follows its ecosystem's standard; the memory bank names are a project requirement · 2026-11-20.
- **Coding agent in neutral paths**: `AGENTS.md` and `.agents/` (rules, skills); no files specific to a particular tool are versioned · `AGENTS.md` is an open standard, the project requires `.agents/` and the repository is not tied to a vendor · 2026-11-20.
- **Language**: the files the agent reads (`AGENTS.md`, `memory-bank/`, `.agents/`) are in English and are the source of truth. Only stable files have a `.es.md` translation, for the team to read; if they differ, English prevails · A single source for the agent, consistent with `BRIEFING.md`, and fewer tokens · 2026-11-20.

## 6. Technical constraints

- Do not create parallel trees: everything goes in the folder defined by [README.md](../README.md) › Folder guide.
- Secrets only in `.env`, never versioned ([.gitignore](../.gitignore) excludes `.env` and `.env.*`; only `.env.example` may be versioned).
- Real personal data never in the repository (not in `data/raw/` either): only fictitious data ([data/raw/README.md](../data/raw/README.md) › Recommendation).

## 7. To be decided

- Frontend framework.
- Database.
- LLM (Large Language Model) provider.
- Backend architecture: the template suggests a single FastAPI API with routers per domain ([README.md](../README.md) › services/); not adopted yet.
