# Tech context: Nexova Solutions

Contexto técnico del monorepo. El negocio está en [projectbrief.md](projectbrief.md).

Etiquetas: **Existe** · **Sugerencia de la plantilla** · **Pendiente de confirmar**. La sección 1 describe sistemas de Nexova, no del repositorio: solo cita su fuente.

## 1. Sistemas actuales de Nexova

Fuente: [BRIEFING.md](../BRIEFING.md) › How the company is organised y › Technology and Infrastructure.

- Herramientas: HubSpot como CRM (Customer Relationship Management), Zendesk heredado, un ATS (Applicant Tracking System) propio de los años 2010, Google Workspace y hojas de cálculo.
- Formación con PDF (Portable Document Format), Google Form y hoja de cálculo; Recursos Humanos con email y hojas de cálculo; dirección con un informe semanal en PDF hecho a mano.
- Carencias: herramientas sin conectar; sin telemetría ni logging centralizado; los fallos se detectan por los usuarios; despliegues manuales; soporte sin base de conocimiento ni visibilidad en tiempo real.

## 2. Entorno de desarrollo

Fuentes: [devcontainer.json](../.devcontainer/devcontainer.json), [post-create.sh](../.devcontainer/post-create.sh), [README.md](../README.md) › How to start.

- **Existe**: devcontainer apto para Codespaces, imagen `devcontainers/universal:2`, usuario `codespace`, socket de Docker del host montado.
- **Existe**: puertos reenviados 3000, 8000 y 5678. **Pendiente de confirmar**: ningún archivo documenta para qué es cada uno.
- **Existe**: `post-create.sh` activa Corepack y `pnpm@latest`, instala `uv` y ejecuta `uv sync`.
- **Pendiente de confirmar**: `uv sync` necesita un `pyproject.toml` y el repositorio no tiene ninguno.

## 3. Stack del monorepo

| Elemento                            | Etiqueta                                  | Fuente                                                                                                                      |
| ----------------------------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Python                              | Existe                                    | [devcontainer.json](../.devcontainer/devcontainer.json), [pandas_clean.py](../skills/data-analysis/scripts/pandas_clean.py) |
| TypeScript                          | Existe                                    | [index.ts](../packages/shared/types/index.ts)                                                                               |
| uv (gestor Python)                  | Existe (instalado)                        | [post-create.sh](../.devcontainer/post-create.sh)                                                                           |
| pnpm (gestor JavaScript/TypeScript) | Existe (instalado); sin workspace en raíz | [post-create.sh](../.devcontainer/post-create.sh); [README.md](../README.md) › Current status of the template               |
| `@repo/shared-types`                | Existe                                    | [package.json](../packages/shared/package.json)                                                                             |
| FastAPI, n8n                        | Sugerencia de la plantilla                | [README.md](../README.md) › services/, › workflows/                                                                         |
| `docker-compose.yml`                | Sugerencia de la plantilla (no existe)    | [README.md](../README.md) › Root files                                                                                      |

**Pendiente de confirmar**: `main` y `types` de `@repo/shared-types` apuntan a `index.ts`, pero el archivo está en `types/index.ts`.

## 4. Mapa de la capa de aplicación

Fuente: [README.md](../README.md) › Folder guide y contenido real del repositorio.

| Ruta             | Qué va                                             | Estado                                                    |
| ---------------- | -------------------------------------------------- | --------------------------------------------------------- |
| `uis/website`    | Web pública                                        | no creada                                                 |
| `uis/backoffice` | Aplicación interna de administración               | no creada                                                 |
| `services/`      | APIs (Application Programming Interface) y workers | solo README de plantilla                                  |
| `agents/`        | Un agente por subcarpeta                           | existe (solo `_template/` y `tools/` de plantilla)        |
| `skills/`        | Skills reutilizables (`SKILL.md` y scripts)        | existe (`_template/`, `data-analysis/` y carpetas vacías) |
| `mcps/`          | Servidores MCP (Model Context Protocol)            | solo README de plantilla                                  |
| `workflows/`     | Automatizaciones y orquestación                    | solo README de plantilla                                  |
| `.agents/`       | Configuración del agente de código (rules, skills) | no creada                                                 |

Nota: `skills/` (plantilla) es para skills del producto de inteligencia artificial (IA) de Nexova; las skills del agente de código van en `.agents/skills/`.

## 5. Decisiones de arquitectura

- **Briefing renombrado de `CONTEXT.md` a `BRIEFING.md` (y `BRIEFING.es.md`)** · Requisito del proyecto: `BRIEFING.md` en la raíz · 2026-11-17 (commit e1ecfd0).
- **Convención de nombres**: kebab-case para archivos nuevos (reglas, skills, docs); snake_case para código Python (PEP 8, Python Enhancement Proposal 8); MAYÚSCULAS para archivos meta de la raíz (`README.md`, `AGENTS.md`, `BRIEFING.md`). Excepción: el memory bank conserva sus nombres canónicos (`projectbrief.md`, `techContext.md`, `progress.md`) · Cada convención sigue el estándar de su ecosistema; los nombres del memory bank son requisito del proyecto · 2026-11-20.
- **Agente de código en rutas neutrales**: `AGENTS.md` y `.agents/` (rules, skills); no se versionan archivos propios de una herramienta concreta · `AGENTS.md` es un estándar abierto, el proyecto requiere `.agents/` y el repositorio no queda atado a un proveedor · 2026-11-20.

## 6. Restricciones técnicas

- No crear árboles paralelos: cada cosa va en la carpeta que define [README.md](../README.md) › Folder guide.
- Secretos solo en `.env`, nunca versionado. **Pendiente de confirmar**: [.gitignore](../.gitignore) está vacío; hoy `.env` no está excluido.
- Datos personales reales nunca en el repositorio (tampoco en `data/raw/`): solo ficticios ([data/raw/README.md](../data/raw/README.md) › Recommendation).

## 7. Por decidir

- Framework de frontend.
- Base de datos.
- Proveedor de LLM (Large Language Model).
- Arquitectura del backend: la plantilla sugiere una única API FastAPI con routers por dominio ([README.md](../README.md) › services/); aún no adoptada.
